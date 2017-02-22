---
title: "COlePropertyPage Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COlePropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COlePropertyPage class"
  - "contrôles personnalisés (MFC), propriétés"
  - "displaying properties"
  - "OLE property pages"
  - "propriétés (C++), afficher"
  - "pages de propriétés, OLE"
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COlePropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé pour afficher les propriétés d'un contrôle personnalisé dans une interface graphique, semblable à une boîte de dialogue.  
  
## Syntaxe  
  
```  
class AFX_NOVTABLE COlePropertyPage : public CDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COlePropertyPage::COlePropertyPage](../Topic/COlePropertyPage::COlePropertyPage.md)|Construit un objet `COlePropertyPage`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COlePropertyPage::GetControlStatus](../Topic/COlePropertyPage::GetControlStatus.md)|Indique si l'utilisateur a modifié la valeur dans le contrôle.|  
|[COlePropertyPage::GetObjectArray](../Topic/COlePropertyPage::GetObjectArray.md)|Retourne le tableau d'objets modifié par la page de propriétés.|  
|[COlePropertyPage::GetPageSite](../Topic/COlePropertyPage::GetPageSite.md)|Retourne un pointeur vers l'interface d' `IPropertyPageSite` de la page de propriétés.|  
|[COlePropertyPage::IgnoreApply](../Topic/COlePropertyPage::IgnoreApply.md)|Détermine quel contrôle n'active pas le bouton de l'application.|  
|[COlePropertyPage::IsModified](../Topic/COlePropertyPage::IsModified.md)|Indique si l'utilisateur a modifié la page de propriétés.|  
|[COlePropertyPage::OnEditProperty](../Topic/COlePropertyPage::OnEditProperty.md)|Appelé par l'infrastructure lorsque l'utilisateur modifie une propriété.|  
|[COlePropertyPage::OnHelp](../Topic/COlePropertyPage::OnHelp.md)|Appelé par l'infrastructure lorsque l'utilisateur appelle l'aide.|  
|[COlePropertyPage::OnInitDialog](../Topic/COlePropertyPage::OnInitDialog.md)|Appelé par l'infrastructure lorsque la page de propriétés est initialisée.|  
|[COlePropertyPage::OnObjectsChanged](../Topic/COlePropertyPage::OnObjectsChanged.md)|Appelé par l'infrastructure lorsqu'un autre contrôle OLE, avec de nouvelles propriétés, est sélectionnez.|  
|[COlePropertyPage::OnSetPageSite](../Topic/COlePropertyPage::OnSetPageSite.md)|Appelé par l'infrastructure lorsque le frame de propriété fournit le site de la page.|  
|[COlePropertyPage::SetControlStatus](../Topic/COlePropertyPage::SetControlStatus.md)|Place une balise qui indique si l'utilisateur a modifié la valeur dans le contrôle.|  
|[COlePropertyPage::SetDialogResource](../Topic/COlePropertyPage::SetDialogResource.md)|Définit la ressource de boîte de dialogue de la page de propriétés.|  
|[COlePropertyPage::SetHelpInfo](../Topic/COlePropertyPage::SetHelpInfo.md)|Définit le résumé texte d'aide de la page de propriétés, le nom de son fichier d'aide, et son contexte d'aide.|  
|[COlePropertyPage::SetModifiedFlag](../Topic/COlePropertyPage::SetModifiedFlag.md)|Place une balise qui indique si l'utilisateur a modifié la page de propriétés.|  
|[COlePropertyPage::SetPageName](../Topic/COlePropertyPage::SetPageName.md)|Définit le nom de la page de propriétés \(légende\).|  
  
## Notes  
 Par exemple, une page de propriétés peut inclure un contrôle d'édition qui permet à l'utilisateur d'afficher et de modifier la propriété de la légende du contrôle.  
  
 Chaque propriété personnalisées ou de contrôle des magasins peut avoir un contrôle de boîte de dialogue qui permet à l'utilisateur du contrôle pour afficher la valeur de propriété actuelle et pour modifier cette valeur si nécessaire.  
  
 Pour plus d'informations sur l'utilisation `COlePropertyPage`, consultez l'article [Contrôles ActiveX : pages de propriétés](../../mfc/mfc-activex-controls-property-pages.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `COlePropertyPage`  
  
## Configuration requise  
 **Header:** afxctl.h  
  
## Voir aussi  
 [exemple MFC CIRC3](../../top/visual-cpp-samples.md)   
 [exemple MFC TESTHELP](../../top/visual-cpp-samples.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)