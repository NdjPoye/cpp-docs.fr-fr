---
title: Classe de CMFCRibbonCustomizeDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetThisClass
- CMFCRibbonCustomizeDialog
- ~CMFCRibbonCustomizeDialog
- CMFCRibbonCustomizeDialog::GetThisClass
- CMFCRibbonCustomizeDialog.~CMFCRibbonCustomizeDialog
- CMFCRibbonCustomizeDialog.GetThisClass
- CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCustomizeDialog class
- CMFCRibbonCustomizeDialog class, destructor
- ~CMFCRibbonCustomizeDialog destructor
- GetThisClass method
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
caps.latest.revision: 22
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
ms.openlocfilehash: d27247f89901adad1778313cdde6fe206a569f0d
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncustomizedialog-class"></a>CMFCRibbonCustomizeDialog (classe)
Affiche le ruban **personnaliser** page.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](#cmfcribboncustomizedialog)|Construit un objet `CMFCRibbonCustomizeDialog`.|  
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCRibbonCustomizeDialog::GetThisClass`|Utilisé par le framework d’obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet associé à ce type de classe.|  
  
## <a name="remarks"></a>Notes  
 MFC instancie automatiquement cette classe si vous ne traitez pas le message AFX_WM_ON_RIBBON_CUSTOMIZE, ou si vous retournez 0 à partir du Gestionnaire de messages.  
  
 Si vous souhaitez utiliser cette classe dans votre application pour afficher le ruban **personnaliser** boîte de dialogue zone, instancier et appeler le `DoModal` (méthode).  
  
 Cette classe est dérivée de [CMFCPropertySheet classe](../../mfc/reference/cmfcpropertysheet-class.md), vous pouvez ajouter des pages personnalisées en utilisant la `CMFCPropertySheet` API.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
 [CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxribboncustomizedialog.h  
  
##  <a name="a-namecmfcribboncustomizedialoga--cmfcribboncustomizedialogcmfcribboncustomizedialog"></a><a name="cmfcribboncustomizedialog"></a>CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog  
 Construit un objet `CMFCRibbonCustomizeDialog`.  
  
```  
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,  
    CMFCRibbonBar* pRibbon);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWndParent`  
 Pointeur vers la fenêtre parente (généralement le frame principal).  
  
 [in] `pRibbon`  
 Un pointeur vers la `CMFCRibbonBar` qui doit être personnalisé.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment construire un `CMFCRibbonCustomizeDialog` objet.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#18;](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]  
  
### <a name="remarks"></a>Notes  
 Le constructeur instancie un [CMFCRibbonCustomizePropertyPage classe](../../mfc/reference/cmfcribboncustomizepropertypage-class.md) de l’objet et l’ajoute à la collection de pages de feuille de propriétés.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

