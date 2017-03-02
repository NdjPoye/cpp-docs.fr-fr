---
title: Structure de CMFCTabToolTipInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabToolTipInfo
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
caps.latest.revision: 27
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b9750cd9369313a3ed6ea9474d401cd0068a75fa
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctabtooltipinfo-structure"></a>Structure de CMFCTabToolTipInfo
Cette structure fournit des informations sur l’onglet MDI qui pointe sur l’utilisateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct CMFCTabToolTipInfo  
```  
  
## <a name="members"></a>Membres  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCTabToolTipInfo::m_nTabIndex](#m_ntabindex)|Spécifie l’index du contrôle onglet.|  
|[CMFCTabToolTipInfo::m_pTabWnd](#m_ptabwnd)|Pointeur vers le contrôle onglet.|  
|[CMFCTabToolTipInfo::m_strText](#m_strtext)|Le texte info-bulle.|  
  
## <a name="remarks"></a>Remarques  
 Un pointeur vers un `CMFCTabToolTipInfo` structure est passée comme paramètre de la `AFX_WM_ON_GET_TAB_TOOLTIP` message. Ce message est généré lorsque les onglets MDI sont activés et l’utilisateur pointe sur un contrôle onglet.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment `CMFCTabToolTipInfo` est utilisée dans le [exemple MDITabsDemo : Application de MDI avec onglets MFC](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo n °&2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxbasetabctrl.h  
  
##  <a name="a-namemntabindexa--cmfctabtooltipinfomntabindex"></a><a name="m_ntabindex"></a>CMFCTabToolTipInfo::m_nTabIndex  
 Spécifie l’index du contrôle onglet.  
  
```  
int m_nTabIndex;  
```  
  
### <a name="remarks"></a>Notes  
 Index de l’onglet sur lequel l’utilisateur pointe.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment `m_nTabIndex` est utilisée dans le [exemple MDITabsDemo : Application de MDI avec onglets MFC](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo n °&2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="a-namemptabwnda--cmfctabtooltipinfomptabwnd"></a><a name="m_ptabwnd"></a>CMFCTabToolTipInfo::m_pTabWnd  
 Pointeur vers le contrôle onglet.  
  
```  
CMFCBaseTabCtrl* m_pTabWnd;  
```  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment `m_pTabWnd` est utilisée dans le [exemple MDITabsDemo : Application de MDI avec onglets MFC](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo n °&2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="a-namemstrtexta--cmfctabtooltipinfomstrtext"></a><a name="m_strtext"></a>CMFCTabToolTipInfo::m_strText  
 Le texte info-bulle.  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>Remarques  
 Si la chaîne est vide, l’info-bulle s’affiche pas.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment `m_strText` est utilisée dans le [exemple MDITabsDemo : Application de MDI avec onglets MFC](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo n °&2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

