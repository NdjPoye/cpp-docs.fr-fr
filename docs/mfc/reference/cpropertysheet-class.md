---
title: "CPropertySheet Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPropertySheet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPropertySheet class"
  - "boîtes de dialogue, onglets"
  - "feuilles de propriétés, CPropertySheet class"
  - "boîtes de dialogue avec onglets"
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
caps.latest.revision: 30
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPropertySheet Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente des feuilles de propriétés, également appelé des boîtes de dialogue d'onglet.  
  
## Syntaxe  
  
```  
class CPropertySheet : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPropertySheet::CPropertySheet](../Topic/CPropertySheet::CPropertySheet.md)|Construit un objet `CPropertySheet`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md)|Ajoute une page à une feuille de propriétés.|  
|[CPropertySheet::Construct](../Topic/CPropertySheet::Construct.md)|Construit un objet `CPropertySheet`.|  
|[CPropertySheet::Create](../Topic/CPropertySheet::Create.md)|Affiche une feuille de propriétés non modale.|  
|[CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md)|Affiche une feuille de propriétés modale.|  
|[CPropertySheet::EnableStackedTabs](../Topic/CPropertySheet::EnableStackedTabs.md)|Indique si les utilisations de feuille de propriétés empilées ou des tabulations de défilement.|  
|[CPropertySheet::EndDialog](../Topic/CPropertySheet::EndDialog.md)|Termine la feuille de propriétés.|  
|[CPropertySheet::GetActiveIndex](../Topic/CPropertySheet::GetActiveIndex.md)|Extrait l'index de la page active de la feuille de propriétés.|  
|[CPropertySheet::GetActivePage](../Topic/CPropertySheet::GetActivePage.md)|Retourne l'objet de la page active.|  
|[CPropertySheet::GetPage](../Topic/CPropertySheet::GetPage.md)|Extrait un pointeur vers la page spécifiée.|  
|[CPropertySheet::GetPageCount](../Topic/CPropertySheet::GetPageCount.md)|Récupère le nombre de pages dans la feuille de propriétés.|  
|[CPropertySheet::GetPageIndex](../Topic/CPropertySheet::GetPageIndex.md)|Extrait l'index de la page spécifiée de la feuille de propriétés.|  
|[CPropertySheet::GetTabControl](../Topic/CPropertySheet::GetTabControl.md)|Extrait un pointeur vers un contrôle onglet.|  
|[CPropertySheet::MapDialogRect](../Topic/CPropertySheet::MapDialogRect.md)|Convertit les unités de boîte de dialogue d'un rectangle pour examiner les unités.|  
|[CPropertySheet::OnInitDialog](../Topic/CPropertySheet::OnInitDialog.md)|Substitution pour augmenter l'initialisation de feuille de propriétés.|  
|[CPropertySheet::PressButton](../Topic/CPropertySheet::PressButton.md)|Décrit le choix du bouton spécifié dans une feuille de propriétés.|  
|[CPropertySheet::RemovePage](../Topic/CPropertySheet::RemovePage.md)|Supprime une page de la feuille de propriétés.|  
|[CPropertySheet::SetActivePage](../Topic/CPropertySheet::SetActivePage.md)|Définit par programme l'objet page active.|  
|[CPropertySheet::SetFinishText](../Topic/CPropertySheet::SetFinishText.md)|Définit le texte du bouton terminé.|  
|[CPropertySheet::SetTitle](../Topic/CPropertySheet::SetTitle.md)|Définit la légende de la feuille de propriétés.|  
|[CPropertySheet::SetWizardButtons](../Topic/CPropertySheet::SetWizardButtons.md)|Active les boutons de l'assistant.|  
|[CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md)|Active le mode d'assistant.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPropertySheet::m\_psh](../Topic/CPropertySheet::m_psh.md)|La structure de [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) windows.  Fournit l'accès aux paramètres de base de feuille de propriétés.|  
  
## Notes  
 Une feuille de propriétés se compose d'un objet d' `CPropertySheet` et d'un ou plusieurs objets de [CPropertyPage](../../mfc/reference/cpropertypage-class.md) .  L'infrastructure affiche une feuille de propriétés comme fenêtre avec un ensemble d'index de tabulation et une zone qui contient la page sélectionnée.  L'utilisateur navigue vers une page spécifique à l'aide de la table appropriée.  
  
 `CPropertySheet` fournit la prise en charge de la structure développée de [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) introduite dans [!INCLUDE[Win98](../../mfc/reference/includes/win98_md.md)] et Windows NT 2000.  La structure contient les balises et des membres supplémentaires qui prennent en charge l'utilisation d'une image d'arrière\-plan « filigrane ».  
  
 Pour afficher ces nouvelles images automatiquement dans votre objet de feuille de propriétés, passez les valeurs valides pour les images de bitmap et de la palette dans l'appel à [CPropertySheet::Construct](../Topic/CPropertySheet::Construct.md) ou à [CPropertySheet::CPropertySheet](../Topic/CPropertySheet::CPropertySheet.md).  
  
 Bien `CPropertySheet` ne soit pas dérivé de [CDialog](../../mfc/reference/cdialog-class.md), gérer un objet d' `CPropertySheet` est semblable à gérer un objet d' `CDialog` .  Par exemple, la création d'une feuille de propriétés requiert la construction en deux parties : appelez le constructeur, puis appelez [DoModal](../Topic/CPropertySheet::DoModal.md) d'une feuille de propriétés modale ou [Create](../Topic/CPropertySheet::Create.md) d'une feuille de propriétés non modale.  `CPropertySheet` deux types de constructeurs : [CPropertySheet::Construct](../Topic/CPropertySheet::Construct.md) et [CPropertySheet::CPropertySheet](../Topic/CPropertySheet::CPropertySheet.md).  
  
 Lorsque vous construisez un objet d' `CPropertySheet` , un certain [Styles de fenêtre](../../mfc/reference/window-styles.md) peut provoquer une exception de première chance.  Cela résulte du système vous essayez de modifier le style de feuille de propriétés avant que la feuille créée.  Pour éviter cette exception, assurez \-vous que vous définissez les styles suivants lorsque vous créez votre `CPropertySheet`:  
  
-   DS\_3DLOOK  
  
-   DS\_CONTROL  
  
-   WS\_CHILD  
  
-   WS\_TABSTOP  
  
 Les styles suivants sont facultatifs, et n'entraîneront pas d'exceptions de première chance :  
  
-   DS\_SHELLFONT  
  
-   DS\_LOCALEDIT  
  
-   WS\_CLIPCHILDREN  
  
 Il est interdit un autre `Window Styles` et vous ne devez pas les activer.  
  
 Échange des données entre un objet d' `CPropertySheet` et un objet externe sont semblables aux données avec un échange objet d' `CDialog` .  La différence importante est que les paramètres d'une feuille de propriétés sont en général des variables membres d'objets d' `CPropertyPage` plutôt que de l'objet d' `CPropertySheet` lui\-même.  
  
 Vous pouvez créer un type de boîte de dialogue d'onglet appelé un assistant, qui se compose d'une feuille de propriétés avec une séquence de pages de propriétés qui guident l'utilisateur à travers les étapes d'une opération, par exemple configurer un périphérique ou créer un bulletin d'informations.  Dans une boîte de dialogue de type assistant onglet, les pages de propriétés n'ont pas les onglets, et uniquement une page de propriétés est visible à la fois.  Aussi, au lieu d'avoir **OK** et des boutons **Appliquer maintenant** , une boîte de dialogue de type assistant onglet comporte un bouton **Arrière** , un bouton **Suivant** ou **Terminé** , un bouton **Annuler** , et un bouton **Aide** .  
  
 Pour créer une boîte de dialogue de type assistant, suivez les mêmes étapes que vous suivriez pour créer une feuille de propriétés standard, mais l'appel [SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md) avant d'appeler [DoModal](../Topic/CPropertySheet::DoModal.md).  Pour permettre aux boutons de l'assistant, à l'appel [SetWizardButtons](../Topic/CPropertySheet::SetWizardButtons.md), à l'aide de balises de personnaliser leur fonction et apparence.  Pour activer le bouton **Terminé** , appelez [SetFinishText](../Topic/CPropertySheet::SetFinishText.md) une fois que l'utilisateur a agi sur la dernière page de l'assistant.  
  
 Pour plus d'informations sur l'utilisation des objets d' `CPropertySheet` , consultez l'article [feuilles de propriétés et pages de propriétés](../../mfc/property-sheets-and-property-pages-in-mfc.md).  En outre, consultez l'article de la Base de connaissances Q146916 : HOWTO : Créez un CPropertySheet non modale avec les boutons et l'article standard Q300606 : HOWTO : Concevez une feuille de propriétés redimensionnable MFC.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPropertySheet`  
  
## Configuration requise  
 **en\-tête :** afxdlgs.h  
  
## Voir aussi  
 [MFC exemple CMNCTRL1](../../top/visual-cpp-samples.md)   
 [MFC exemple CMNCTRL2](../../top/visual-cpp-samples.md)   
 [exemple MFC PROPDLG](../../top/visual-cpp-samples.md)   
 [MFC exemple SNAPVW](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)