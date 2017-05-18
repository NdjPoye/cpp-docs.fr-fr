---
title: Classe de CMFCRibbonCustomizePropertyPage | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::AddCustomCategory
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::OnOK
dev_langs:
- C++
helpviewer_keywords:
- ~CMFCRibbonCustomizePropertyPage destructor
- CMFCRibbonCustomizePropertyPage class, destructor
- GetThisClass method
- CreateObject method
- CMFCRibbonCustomizePropertyPage class
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
caps.latest.revision: 26
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 83323142441de13140383152a32122bf1644003f
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncustomizepropertypage-class"></a>CMFCRibbonCustomizePropertyPage (classe)
Implémente une page personnalisée pour le **personnaliser** boîte de dialogue dans les applications basées sur le ruban.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|Construit un objet `CMFCRibbonCustomizePropertyPage`.|  
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](#addcustomcategory)|Ajoute une catégorie personnalisée de la **commandes** zone de liste déroulante.|  
|`CMFCRibbonCustomizePropertyPage::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|Utilisé par le framework d’obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet associé à ce type de classe.|  
|[CMFCRibbonCustomizePropertyPage::OnOK](#onok)|Appelée par le système lorsqu’un utilisateur clique **OK** sur la **personnaliser** boîte de dialogue.|  
  
## <a name="remarks"></a>Notes  
 Si vous souhaitez ajouter des commandes personnalisées à la **personnaliser** boîte de dialogue, vous devez gérer le message AFX_WM_ON_RIBBON_CUSTOMIZE. Dans le Gestionnaire de messages, instanciez un `CMFCRibbonCustomizePropertyPage` objet sur la pile. Créer une liste de commandes personnalisés, puis appelez `AddCustomCategory` pour ajouter la nouvelle page à la **personnaliser** boîte de dialogue.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment construire un `CMFCRibbonCustomizePropertyPage` objet et ajouter une catégorie personnalisée.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#22;](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
 [CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxribboncustomizedialog.h  
  
##  <a name="addcustomcategory"></a>CMFCRibbonCustomizePropertyPage::AddCustomCategory  
 Ajoute une catégorie personnalisée de la **commandes** zone de liste déroulante.  
  
```  
void AddCustomCategory(
    LPCTSTR lpszName,  
    const CList<UINT, UINT>& lstIDS);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `lpszName`|Spécifie le nom de la catégorie personnalisée.|  
|[in] `lstIDS`|Contient l’ID de commandes du ruban à afficher dans la catégorie personnalisée.|  
  
### <a name="remarks"></a>Notes  
 Cette méthode ajoute une catégorie nommée `lpszName` à la **commandes** zone de liste déroulante. Lorsque l’utilisateur sélectionne la catégorie, les commandes spécifiées dans `lstIDS` s’affichent dans la liste de commandes.  
  
##  <a name="cmfcribboncustomizepropertypage"></a>CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage  
 Construit un objet `CMFCRibbonCustomizePropertyPage`.  
  
```  
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pRibbonBar`  
 Un pointeur vers un contrôle de ruban pour laquelle les options pour personnaliser.  
  
##  <a name="onok"></a>CMFCRibbonCustomizePropertyPage::OnOK  
 Calleld par le système lorsqu’un utilisateur clique **OK** sur la **personnaliser** boîte de dialogue.  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut applique les options sélectionnées dans la **personnaliser** boîte de dialogue pour la barre d’outils Accès rapide.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

