---
title: Classe de CMFCAcceleratorKey | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
dev_langs:
- C++
helpviewer_keywords:
- CMFCAcceleratorKey class
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
caps.latest.revision: 36
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 7baa210acfabe8f17e2ab747fd98fe463c2907a2
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey (classe)
Une classe d’assistance qui implémente la mise en forme et mappage du clavier virtuel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCAcceleratorKey : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|Construit un objet `CMFCAcceleratorKey`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCAcceleratorKey::Format](#format)|Convertit la structure de touche d’accès rapide à la représentation visuelle.|  
|[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)|Définit la touche de raccourci pour la `CMFCAcceleratorKey` objet.|  
  
## <a name="remarks"></a>Notes  
 Touches d’accès rapide sont également appelées touches de raccourci. Si vous souhaitez afficher les raccourcis clavier qui accède à un utilisateur, le [CMFCAcceleratorKeyAssignCtrl classe](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) maps raccourcis clavier, tels que Alt + Maj + S, dans un format de texte personnalisé, tel que « Alt + Maj + S ». Chaque `CMFCAcceleratorKey` objet mappe une touche de raccourci unique au format texte.  
  
 Pour plus d’informations sur l’utilisation des touches de raccourci et les tables d’accélérateurs, consultez [CKeyboardManager classe](../../mfc/reference/ckeyboardmanager-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment construire un `CMFCAcceleratorKey` objet et comment utiliser ses `Format` méthode.  
  
 [!code-cpp[30 NVC_MFC_RibbonApp](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCAcceleratorKey`   
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxacceleratorkey.h  
  
##  <a name="cmfcacceleratorkey"></a>CMFCAcceleratorKey::CMFCAcceleratorKey  
 Construit un [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) objet.  
  
```  
CMFCAcceleratorKey();  
CMFCAcceleratorKey(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpAccel`  
 Pointeur vers une touche de raccourci.  
  
### <a name="remarks"></a>Notes  
 Si vous ne fournissez pas une touche de raccourci lorsque vous créez un `CMFCAccleratorKey`, utilisez la [CMFCAcceleratorKey::SetAccelerator](#setaccelerator) pour associer une touche de raccourci avec votre `CMFCAcceleratorKey` objet.  
  
##  <a name="format"></a>CMFCAcceleratorKey::Format  
 Convertit la structure de touche d’accès rapide à sa valeur de chaîne associée.  
  
```  
void Format(CString& str) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `str`  
 Une référence à un `CString` objet où la méthode écrit le raccourci traduites.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode récupère le format de chaîne de la touche de raccourci. Vous pouvez définir le format de chaîne d’un [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) à l’aide de la méthode ou le constructeur de l’objet [CMFCAcceleratorKey::SetAccelerator](#setaccelerator).  
  
##  <a name="setaccelerator"></a>CMFCAcceleratorKey::SetAccelerator  
 Définit la touche de raccourci pour le [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) objet.  
  
```  
void SetAccelerator(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpAccel`  
 Pointeur vers une touche de raccourci.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour définir la touche de raccourci pour un `CMFCAcceleratorKey` si vous n’avez pas fourni une touche de raccourci lorsque vous avez créé le `CMFCAcceleratorKey`.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager (classe)](../../mfc/reference/ckeyboardmanager-class.md)

