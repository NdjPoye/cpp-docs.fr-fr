---
title: "CMFCRibbonEdit Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonEdit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonEdit class"
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CMFCRibbonEdit Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente un contrôle d'édition qui se trouve sur une barre de ruban.  
  
## Syntaxe  
  
```  
class CMFCRibbonEdit : public CMFCRibbonButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonEdit::CMFCRibbonEdit](../Topic/CMFCRibbonEdit::CMFCRibbonEdit.md)|Construit un objet `CMFCRibbonEdit`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonEdit::CanBeStretched](../Topic/CMFCRibbonEdit::CanBeStretched.md)|Indique si la hauteur du contrôle d' `CMFCRibbonEdit` peut grimper verticalement jusqu'à la hauteur d'une ligne de ruban.|  
|[CMFCRibbonEdit::CMFCRibbonEdit](../Topic/CMFCRibbonEdit::CMFCRibbonEdit.md)|Construit un objet `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::CopyFrom](../Topic/CMFCRibbonEdit::CopyFrom.md)|Copie l'état de l'objet spécifié d' `CMFCRibbonEdit` à l'objet actuel d' `CMFCRibbonEdit` .|  
|[CMFCRibbonEdit::CreateEdit](../Topic/CMFCRibbonEdit::CreateEdit.md)|Crée une nouvelle zone de texte de l'objet d' `CMFCRibbonEdit` .|  
|[CMFCRibbonEdit::DestroyCtrl](../Topic/CMFCRibbonEdit::DestroyCtrl.md)|Détruit l'objet `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::DropDownList](../Topic/CMFCRibbonEdit::DropDownList.md)|Supprime le bas une zone de liste.|  
|[CMFCRibbonEdit::EnableSpinButtons](../Topic/CMFCRibbonEdit::EnableSpinButtons.md)|Active et définit l'intervalle de la toupie de la zone de texte.|  
|[CMFCRibbonEdit::GetCompactSize](../Topic/CMFCRibbonEdit::GetCompactSize.md)|Extrait la taille compacte de l'objet d' `CFMCRibbonEdit` .|  
|[CMFCRibbonEdit::GetEditText](../Topic/CMFCRibbonEdit::GetEditText.md)|Extrait le texte dans la zone de texte.|  
|[CMFCRibbonEdit::GetIntermediateSize](../Topic/CMFCRibbonEdit::GetIntermediateSize.md)|Extrait la taille intermédiaire de l'objet d' `CMFCRibbonEdit` .|  
|[CMFCRibbonEdit::GetTextAlign](../Topic/CMFCRibbonEdit::GetTextAlign.md)|Extrait l'alignement du texte dans la zone de texte.|  
|[CMFCRibbonEdit::GetWidth](../Topic/CMFCRibbonEdit::GetWidth.md)|Extrait la largeur, en pixels, du contrôle d' `CMFCRibbonEdit` .|  
|[CMFCRibbonEdit::HasCompactMode](../Topic/CMFCRibbonEdit::HasCompactMode.md)|Indique si la taille d'affichage du contrôle d' `CMFCRibbonEdit` peut être compacte.|  
|[CMFCRibbonEdit::HasFocus](../Topic/CMFCRibbonEdit::HasFocus.md)|Indique si le contrôle d' `CMFCRIbbonEdit` a le focus.|  
|[CMFCRibbonEdit::HasLargeMode](../Topic/CMFCRibbonEdit::HasLargeMode.md)|Indique si la taille d'affichage du contrôle d' `CMFCRibbonEdit` peut être importante.|  
|[CMFCRibbonEdit::HasSpinButtons](../Topic/CMFCRibbonEdit::HasSpinButtons.md)|Indique si la zone de texte a une toupie.|  
|[CMFCRibbonEdit::IsHighlighted](../Topic/CMFCRibbonEdit::IsHighlighted.md)|Indique si le contrôle d' `CMFCRibbonEdit` est mis en surbrillance.|  
|[CMFCRibbonEdit::OnAfterChangeRect](../Topic/CMFCRibbonEdit::OnAfterChangeRect.md)|Appelé par l'infrastructure lorsque les dimensions du rectangle d'affichage pour le contrôle d' `CMFCRibbonEdit` .|  
|[CMFCRibbonEdit::OnDraw](../Topic/CMFCRibbonEdit::OnDraw.md)|Appelé par l'infrastructure pour dessiner le contrôle d' `CMFCRibbonEdit` .|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](../Topic/CMFCRibbonEdit::OnDrawLabelAndImage.md)|Appelé par l'infrastructure pour dessiner l'étiquette et l'image pour le contrôle d' `CMFCRibbonEdit` .|  
|[CMFCRibbonEdit::OnDrawOnList](../Topic/CMFCRibbonEdit::OnDrawOnList.md)|Appelé par l'infrastructure pour dessiner le contrôle d' `CMFCRibbonEdit` dans une zone de liste de commandes.|  
|[CMFCRibbonEdit::OnEnable](../Topic/CMFCRibbonEdit::OnEnable.md)|Appelé par l'infrastructure pour activer ou désactiver le contrôle d' `CMFCRibbonEdit` .|  
|[CMFCRibbonEdit::OnHighlight](../Topic/CMFCRibbonEdit::OnHighlight.md)|Appelé par l'infrastructure lorsque le pointeur écrit ou permet de les limites du contrôle d' `CMFCRibbonEdit` .|  
|[CMFCRibbonEdit::OnKey](../Topic/CMFCRibbonEdit::OnKey.md)|Appelé par l'infrastructure lorsque l'utilisateur appuie sur un keytip et le contrôle d' `CMFCRibbonEdit` a le focus.|  
|[CMFCRibbonEdit::OnLButtonDown](../Topic/CMFCRibbonEdit::OnLButtonDown.md)|Appelé par l'infrastructure pour gérer le contrôle d' `CMFCRibbonEdit` lorsque l'utilisateur appuie sur le bouton gauche de la souris sur le contrôle.|  
|[CMFCRibbonEdit::OnLButtonUp](../Topic/CMFCRibbonEdit::OnLButtonUp.md)|Appelé par l'infrastructure lorsque l'utilisateur relâche le bouton gauche de la souris.|  
|[CMFCRibbonEdit::OnRTLChanged](../Topic/CMFCRibbonEdit::OnRTLChanged.md)|Appelé par l'infrastructure pour gérer le contrôle d' `CMFCRibbonEdit` lorsque la disposition change la direction.|  
|[CMFCRibbonEdit::OnShow](../Topic/CMFCRibbonEdit::OnShow.md)|Appelé par l'infrastructure pour afficher ou masquer le contrôle d' `CMFCRibbonEdit` .|  
|[CMFCRibbonEdit::Redraw](../Topic/CMFCRibbonEdit::Redraw.md)|Met à jour l'affichage du contrôle d' `CMFCRibbonEdit` .|  
|[CMFCRibbonEdit::SetACCData](../Topic/CMFCRibbonEdit::SetACCData.md)|Définit les données d'accessibilité pour l'objet d' `CMFCRibbonEdit` .|  
|[CMFCRibbonEdit::SetEditText](../Topic/CMFCRibbonEdit::SetEditText.md)|Définit le texte dans la zone de texte.|  
|[CMFCRibbonEdit::SetTextAlign](../Topic/CMFCRibbonEdit::SetTextAlign.md)|Définit l'alignement de texte de la zone de texte.|  
|[CMFCRibbonEdit::SetWidth](../Topic/CMFCRibbonEdit::SetWidth.md)|Définit la largeur de la zone de texte du contrôle d' `CMFCRibbonEdit` .|  
  
## Notes  
  
## Exemple  
 L'exemple suivant montre comment construire un objet d' `CMFCRibbonEdit` , afficher des toupies en regard de le contrôle d'édition, et définir le texte du contrôle d'édition.  Cet extrait de code fait partie d' [Exemple 2007 de démonstration de MS Office](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/CPP/cmfcribbonedit-class_1.cpp)]  
  
## Configuration requise  
 **en\-tête :** afxRibbonEdit.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)