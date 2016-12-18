---
title: "Classe CMFCRibbonColorButton | Microsoft Docs"
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
  - "CMFCRibbonColorButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonColorButton (classe)"
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
caps.latest.revision: 36
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CMFCRibbonColorButton
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe `CMFCRibbonColorButton` implémente un bouton de couleur que vous pouvez ajouter à une barre de ruban. Le bouton de couleur du ruban affiche un menu déroulant qui contient une ou plusieurs palettes de couleurs.  
  
## Syntaxe  
  
```  
class CMFCRibbonColorButton : public CMFCRibbonGallery  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonColorButton::CMFCRibbonColorButton](../Topic/CMFCRibbonColorButton::CMFCRibbonColorButton.md)||  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonColorButton::AddColorsGroup](../Topic/CMFCRibbonColorButton::AddColorsGroup.md)|Ajoute un groupe de couleurs dans la zone de couleur normale.|  
|[CMFCRibbonColorButton::EnableAutomaticButton](../Topic/CMFCRibbonColorButton::EnableAutomaticButton.md)|Spécifie si le bouton **Automatique** est activé.|  
|[CMFCRibbonColorButton::EnableOtherButton](../Topic/CMFCRibbonColorButton::EnableOtherButton.md)|Active le bouton **Autres**.|  
|[CMFCRibbonColorButton::GetAutomaticColor](../Topic/CMFCRibbonColorButton::GetAutomaticColor.md)||  
|[CMFCRibbonColorButton::GetColor](../Topic/CMFCRibbonColorButton::GetColor.md)|Retourne la couleur actuellement sélectionnée.|  
|[CMFCRibbonColorButton::GetColorBoxSize](../Topic/CMFCRibbonColorButton::GetColorBoxSize.md)|Retourne la taille des éléments de couleur qui apparaissent dans la barre de couleurs.|  
|[CMFCRibbonColorButton::GetColumns](../Topic/CMFCRibbonColorButton::GetColumns.md)||  
|[CMFCRibbonColorButton::GetHighlightedColor](../Topic/CMFCRibbonColorButton::GetHighlightedColor.md)|Retourne la couleur de l’élément actuellement sélectionné dans la palette de couleurs contextuelle.|  
|[CMFCRibbonColorButton::RemoveAllColorGroups](../Topic/CMFCRibbonColorButton::RemoveAllColorGroups.md)|Supprime tous les groupes de couleurs de la zone de couleur normale.|  
|[CMFCRibbonColorButton::SetColor](../Topic/CMFCRibbonColorButton::SetColor.md)|Sélectionne une couleur dans la zone de couleur normale.|  
|[CMFCRibbonColorButton::SetColorBoxSize](../Topic/CMFCRibbonColorButton::SetColorBoxSize.md)|Définit la taille de tous les éléments de couleur qui apparaissent dans la barre de couleurs.|  
|[CMFCRibbonColorButton::SetColorName](../Topic/CMFCRibbonColorButton::SetColorName.md)||  
|[CMFCRibbonColorButton::SetColumns](../Topic/CMFCRibbonColorButton::SetColumns.md)||  
|[CMFCRibbonColorButton::SetDocumentColors](../Topic/CMFCRibbonColorButton::SetDocumentColors.md)|Spécifie une liste de valeurs RVB à afficher dans la zone de couleur du document.|  
|[CMFCRibbonColorButton::SetPalette](../Topic/CMFCRibbonColorButton::SetPalette.md)||  
|[CMFCRibbonColorButton::UpdateColor](../Topic/CMFCRibbonColorButton::UpdateColor.md)||  
  
## Notes  
 Le bouton de couleur du ruban affiche une barre de couleurs quand un utilisateur clique dessus. Par défaut, cette barre de couleurs contient une palette de sélection de couleurs appelée zone de couleur normale. Si vous le souhaitez, la barre de couleurs peut afficher un bouton **Automatique**, qui permet à l’utilisateur de sélectionner une couleur par défaut, et un bouton **Autres** qui affiche une palette de couleurs contextuelle qui contient des couleurs supplémentaires.  
  
## Exemple  
 L’exemple suivant montre comment utiliser différentes méthodes de la classe `CMFCRibbonColorButton`. L’exemple montre comment construire un objet `CMFCRibbonColorButton`, définir l’image de grande taille, activez le bouton **Automatique**, activer le bouton **Autres**, définir le nombre de colonnes, définir la taille de tous les éléments de couleur qui apparaissent sur la barre de couleurs, ajouter un groupe de couleurs à la zone de couleur normale et spécifier une liste de valeurs RVB à afficher dans la zone de couleur du document. Cet extrait de code fait partie de l’[exemple Draw Client](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/CPP/cmfcribboncolorbutton-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)  
  
## Configuration requise  
 **En\-tête :** afxribboncolorbutton.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery Class](../../mfc/reference/cmfcribbongallery-class.md)