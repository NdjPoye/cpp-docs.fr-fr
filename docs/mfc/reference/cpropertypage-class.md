---
title: "CPropertyPage Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPropertyPage class"
  - "boîtes de dialogue, onglets"
  - "pages de propriétés, CPropertyPage class"
  - "boîtes de dialogue avec onglets"
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CPropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente des pages individuelles d'une feuille de propriétés, sinon appelé une boîte de dialogue d'onglet.  
  
## Syntaxe  
  
```  
class CPropertyPage : public CDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPropertyPage::CPropertyPage](../Topic/CPropertyPage::CPropertyPage.md)|Construit un objet `CPropertyPage`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPropertyPage::CancelToClose](../Topic/CPropertyPage::CancelToClose.md)|Modifie le bouton OK pour lire la fin, et désactive le bouton Annuler, après une modification irrécupérable de la page d'une feuille de propriétés modale.|  
|[CPropertyPage::Construct](../Topic/CPropertyPage::Construct.md)|Construit un objet `CPropertyPage`.  Utilisez `Construct` si vous souhaitez spécifier vos paramètres au moment de l'exécution, ou si vous utilisez des tableaux.|  
|[CPropertyPage::GetPSP](../Topic/CPropertyPage::GetPSP.md)|Extrait la structure de [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) windows associé à l'objet d' `CPropertyPage` .|  
|[CPropertyPage::OnApply](../Topic/CPropertyPage::OnApply.md)|Appelé par l'infrastructure lorsque l'application bouton événements maintenant utilisateur clique dessus.|  
|[CPropertyPage::OnCancel](../Topic/CPropertyPage::OnCancel.md)|Appelé par l'infrastructure lorsque le bouton Annuler est sélectionné.|  
|[CPropertyPage::OnKillActive](../Topic/CPropertyPage::OnKillActive.md)|Appelé par l'infrastructure lorsque la page actuelle n'est plus la page active.  Exécutez ici la validation des données.|  
|[CPropertyPage::OnOK](../Topic/CPropertyPage::OnOK.md)|Appelé par l'infrastructure lorsque OK, s'appliquent désormais, ou le bouton Fermer utilisateur clique dessus.|  
|[CPropertyPage::OnQueryCancel](../Topic/CPropertyPage::OnQueryCancel.md)|Appelé par l'infrastructure lorsque le bouton Annuler est sélectionné, et avant l'annulation a eu lieu.|  
|[CPropertyPage::OnReset](../Topic/CPropertyPage::OnReset.md)|Appelé par l'infrastructure lorsque le bouton Annuler est sélectionné.|  
|[CPropertyPage::OnSetActive](../Topic/CPropertyPage::OnSetActive.md)|Appelé par l'infrastructure lorsque la page est envoyée à la page active.|  
|[CPropertyPage::OnWizardBack](../Topic/CPropertyPage::OnWizardBack.md)|Appelé par l'infrastructure lorsque le bouton précédent utilisateur clique sur lorsque vous utilisez une feuille de propriétés de type assistant.|  
|[CPropertyPage::OnWizardFinish](../Topic/CPropertyPage::OnWizardFinish.md)|Appelé par l'infrastructure lorsque le bouton de fin est effectué sur lorsque vous utilisez une feuille de propriétés de type assistant.|  
|[CPropertyPage::OnWizardNext](../Topic/CPropertyPage::OnWizardNext.md)|Appelé par l'infrastructure lorsque le bouton suivant est effectué sur lorsque vous utilisez une feuille de propriétés de type assistant.|  
|[CPropertyPage::QuerySiblings](../Topic/CPropertyPage::QuerySiblings.md)|Transféré au message chaque page de la feuille de propriétés.|  
|[CPropertyPage::SetModified](../Topic/CPropertyPage::SetModified.md)|L'appel pour exécuter ou déboguer l'application bouton événements maintenant.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPropertyPage::m\_psp](../Topic/CPropertyPage::m_psp.md)|La structure de [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) windows.  Fournit l'accès aux paramètres de page de propriétés.|  
  
## Notes  
 Comme avec les boîtes de dialogue standard, vous dérivez une classe d' `CPropertyPage` pour chaque page dans votre feuille de propriétés.  Pour utiliser `CPropertyPage`\- objets dérivés, créez d'abord un objet de [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) , puis créez ensuite un objet pour chaque page qui est inséré dans la feuille de propriétés.  Appelez [CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md) pour chaque page dans la feuille, puis affichez la feuille de propriétés en appelant [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md) d'une feuille de propriétés modale, ou [CPropertySheet::Create](../Topic/CPropertySheet::Create.md) d'une feuille de propriétés non modale.  
  
 Vous pouvez créer un type de boîte de dialogue d'onglet appelé un assistant, qui se compose d'une feuille de propriétés avec une séquence de pages de propriétés qui guident l'utilisateur à travers les étapes d'une opération, par exemple configurer un périphérique ou créer un bulletin d'informations.  Dans une boîte de dialogue de type assistant onglet, les pages de propriétés n'ont pas les onglets, et uniquement une page de propriétés est visible à la fois.  Aussi, au lieu d'avoir un bouton OK et appliquez maintenant les boutons, une boîte de dialogue de type assistant de tabulation a une précédent, un suivant ou arrête le bouton, et un bouton Annuler.  
  
 Pour plus d'informations sur générer une feuille de propriétés comme un assistant, consultez [CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md).  Pour plus d'informations sur l'utilisation des objets d' `CPropertyPage` , consultez l'article [feuilles de propriétés et pages de propriétés](../../mfc/property-sheets-and-property-pages-in-mfc.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CPropertyPage`  
  
## Configuration requise  
 **Header:** afxdlgs.h  
  
## Voir aussi  
 [MFC exemple CMNCTRL1](../../top/visual-cpp-samples.md)   
 [MFC exemple CMNCTRL2](../../top/visual-cpp-samples.md)   
 [exemple MFC PROPDLG](../../top/visual-cpp-samples.md)   
 [MFC exemple SNAPVW](../../top/visual-cpp-samples.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CPropertySheet Class](../../mfc/reference/cpropertysheet-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md)