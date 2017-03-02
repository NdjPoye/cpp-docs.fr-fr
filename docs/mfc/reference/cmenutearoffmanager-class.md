---
title: Classe de CMenuTearOffManager | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMenuTearOffManager
dev_langs:
- C++
helpviewer_keywords:
- CMenuTearOffManager class
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
caps.latest.revision: 31
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 53677bbea54e428e5f080f5c1f73c576abcf99a5
ms.lasthandoff: 02/24/2017

---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOffManager (classe)
Gère les menus détachables. Un menu détachable est un menu de la barre de menus. L'utilisateur peut supprimer un menu détachable de la barre de menus, provoquant ainsi son flottement.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMenuTearOffManager : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMenuTearOffManager::CMenuTearOffManager](#cmenutearoffmanager)|Construit un objet `CMenuTearOffManager`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMenuTearOffManager::Build](#build)||  
|[CMenuTearOffManager::GetRegPath](#getregpath)||  
|[CMenuTearOffManager::Initialize](#initialize)|Initialise un `CMenuTearOffManager` objet.|  
|[CMenuTearOffManager::IsDynamicID](#isdynamicid)||  
|[CMenuTearOffManager::Parse](#parse)||  
|[CMenuTearOffManager::Reset](#reset)||  
|[CMenuTearOffManager::SetInUse](#setinuse)||  
|[CMenuTearOffManager::SetupTearOffMenus](#setuptearoffmenus)||  
  
## <a name="remarks"></a>Remarques  
 Pour utiliser les menus volants dans votre application, vous devez avoir un `CMenuTearOffManager` objet. Dans la plupart des cas, vous ne créez ou initialiser un `CMenuTearOffManager` directement l’objet. Ceci est géré pour vous lorsque vous appelez le [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) (fonction).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment créer et initialiser un `CMenuTearOffManager` objet en appelant le `CWinAppEX::EnableTearOffMenus` (méthode). Cet extrait de code fait partie de la [exemple du bloc-notes](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&#12;](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenuTearOffManager`   
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxmenutearoffmanager.h  
  
##  <a name="a-namebuilda--cmenutearoffmanagerbuild"></a><a name="build"></a>CMenuTearOffManager::Build  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Build(
    UINT uiTearOffBarID,  
    CString& strText);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiTearOffBarID`  
 [in] `strText`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namecmenutearoffmanagera--cmenutearoffmanagercmenutearoffmanager"></a><a name="cmenutearoffmanager"></a>CMenuTearOffManager::CMenuTearOffManager  
 Construit un [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) objet.  
  
```  
CMenuTearOffManager();
```  
  
### <a name="remarks"></a>Remarques  
 Dans la plupart des cas, ne créez pas une `CMenuTearOffManager` manuellement. L’infrastructure de votre application crée le `CMenuTearOffManager` lorsque vous appelez l’objet [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus).  
  
##  <a name="a-namegetregpatha--cmenutearoffmanagergetregpath"></a><a name="getregpath"></a>CMenuTearOffManager::GetRegPath  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
LPCTSTR GetRegPath() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameinitializea--cmenutearoffmanagerinitialize"></a><a name="initialize"></a>CMenuTearOffManager::Initialize  
 Initialise un [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) objet.  
  
```  
BOOL Initialize(
    LPCTSTR lpszRegEntry,  
    UINT uiTearOffMenuFirst,  
    UINT uiTearOffMenuLast);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszRegEntry`  
 Chaîne qui contient le chemin d’accès d’une entrée de Registre. Vos applications stocke les paramètres pour les barres de détachable dans cette entrée de Registre.  
  
 [in] `uiTearOffMenuFirst`  
 Le premier ID de menu d’un menu volant.  
  
 [in] `uiTearOffMenuLast`  
 Le dernier ID de menu d’un menu volant.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 La plage d’ID de menu à partir de `uiTearOffMenuFirst` à `uiTearOffMenuLast` doit être un intervalle continu. L’intervalle définit le nombre de menus volants qui peuvent s’afficher en même temps dans l’application.  
  
##  <a name="a-nameisdynamicida--cmenutearoffmanagerisdynamicid"></a><a name="isdynamicid"></a>CMenuTearOffManager::IsDynamicID  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsDynamicID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiID`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameparsea--cmenutearoffmanagerparse"></a><a name="parse"></a>CMenuTearOffManager::Parse  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
UINT Parse(CString& str);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `str`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namereseta--cmenutearoffmanagerreset"></a><a name="reset"></a>CMenuTearOffManager::Reset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Reset(HMENU hmenu);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `hmenu`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetinusea--cmenutearoffmanagersetinuse"></a><a name="setinuse"></a>CMenuTearOffManager::SetInUse  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetInUse(
    UINT uiCmdId,  
    BOOL bUse = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdId`  
 [in] `bUse`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetuptearoffmenusa--cmenutearoffmanagersetuptearoffmenus"></a><a name="setuptearoffmenus"></a>CMenuTearOffManager::SetupTearOffMenus  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetupTearOffMenus(HMENU hMenu);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `hMenu`  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx (classe)](../../mfc/reference/cwinappex-class.md)

