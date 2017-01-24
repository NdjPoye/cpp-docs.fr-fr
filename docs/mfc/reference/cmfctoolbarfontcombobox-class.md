---
title: "CMFCToolBarFontComboBox Class | Microsoft Docs"
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
  - "CMFCToolBarFontComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarFontComboBox class"
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
caps.latest.revision: 29
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarFontComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un bouton de barre d'outils qui contient un contrôle zone de liste déroulante qui permet à l'utilisateur de sélectionner une police d'une liste des polices système.  
  
## Syntaxe  
  
```  
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](../Topic/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox.md)|Construit un objet `CMFCToolBarFontComboBox`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarFontComboBox::GetFontDesc](../Topic/CMFCToolBarFontComboBox::GetFontDesc.md)|Retourne un pointeur vers l'objet d' `CMFCFontInfo` pour un index spécifié dans la zone de liste déroulante.|  
|[CMFCToolBarFontComboBox::SetFont](../Topic/CMFCToolBarFontComboBox::SetFont.md)|Sélectionne une police dans la zone de liste déroulante de la police d'après le nom de la police, ou le préfixe et le jeu de caractères de la police.|  
  
### Membres de données  
 [CMFCToolBarFontComboBox::m\_nFontHeight](../Topic/CMFCToolBarFontComboBox::m_nFontHeight.md)  
 La hauteur des caractères dans la zone de liste déroulante de la police.  
  
## Notes  
 Pour ajouter un bouton de zone de liste déroulante de la police à une barre d'outils, suivez ces étapes :  
  
1.  Réservez un ID de ressource factice pour le bouton dans la ressource parente de barre d'outils.  
  
2.  Construisez un objet `CMFCToolBarFontComboBox`.  
  
3.  Dans le gestionnaire de messages qui traite le message d' `AFX_WM_RESETTOOLBAR` , remplacez le bouton d'origine par le nouveau bouton de zone de liste déroulante à l'aide de [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md).  
  
4.  Synchronisez la police sélectionnée dans la zone de liste déroulante avec la police du document à l'aide de la méthode de [CMFCToolBarFontComboBox::SetFont](../Topic/CMFCToolBarFontComboBox::SetFont.md) .  
  
 Pour synchroniser la police du document avec la police sélectionnée dans la zone de liste déroulante, utilisez la méthode de [CMFCToolBarFontComboBox::GetFontDesc](../Topic/CMFCToolBarFontComboBox::GetFontDesc.md) pour récupérer les attributs de la police sélectionnée, puis utiliser ces attributs pour créer un objet de [CFont Class](../../mfc/reference/cfont-class.md) .  
  
 Le bouton de zone de liste déroulante de la police appelle la fonction [EnumFontFamiliesEx](http://msdn.microsoft.com/library/windows/desktop/dd162620) Win32 pour déterminer les polices d'écran et d'imprimante disponibles sur le système.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)  
  
## Configuration requise  
 **en\-tête :** afxtoolbarfontcombobox.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton Class](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo Class](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [Procédure pas à pas : placement de contrôles dans les barres d'outils](../../mfc/walkthrough-putting-controls-on-toolbars.md)