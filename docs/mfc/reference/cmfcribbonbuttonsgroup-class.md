---
title: "CMFCRibbonButtonsGroup, Classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonButtonsGroup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonButtonsGroup, classe"
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
caps.latest.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 36
---
# CMFCRibbonButtonsGroup, Classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCRibbonButtonsGroup` vous permet d'organiser un ensemble de boutons de ruban dans un groupe.  Tous les boutons au groupe sont directement en regard de l'un de l'autre horizontalement et placé dans une bordure.  
  
## Syntaxe  
  
```  
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](../Topic/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup.md)|Construit un objet `CMFCRibbonButtonsGroup`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonButtonsGroup::AddButton](../Topic/CMFCRibbonButtonsGroup::AddButton.md)|Ajoute un bouton à un groupe.|  
|[CMFCRibbonButtonsGroup::AddButtons](../Topic/CMFCRibbonButtonsGroup::AddButtons.md)|Ajoute une liste des boutons à un groupe.|  
|[CMFCRibbonButtonsGroup::GetButton](../Topic/CMFCRibbonButtonsGroup::GetButton.md)|Retourne un pointeur vers le bouton situé à un index spécifié.|  
|[CMFCRibbonButtonsGroup::GetCount](../Topic/CMFCRibbonButtonsGroup::GetCount.md)|Retourne le nombre de boutons au groupe.|  
|[CMFCRibbonButtonsGroup::GetImageSize](../Topic/CMFCRibbonButtonsGroup::GetImageSize.md)|Retourne la taille de l'image des images normales au groupe de ruban \(substitutions [CMFCRibbonBaseElement::GetImageSize](../Topic/CMFCRibbonBaseElement::GetImageSize.md).\)|  
|[CMFCRibbonButtonsGroup::GetRegularSize](../Topic/CMFCRibbonButtonsGroup::GetRegularSize.md)|Retourne la taille normale de l'élément ruban \(substitutions [CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md).\)|  
|[CMFCRibbonButtonsGroup::HasImages](../Topic/CMFCRibbonButtonsGroup::HasImages.md)|Indique si l'objet d' `CMFCRibbonButtonsGroup` contient des images de barre d'outils.|  
|[CMFCRibbonButtonsGroup::OnDrawImage](../Topic/CMFCRibbonButtonsGroup::OnDrawImage.md)|Dessine l'image appropriée pour un bouton spécifié, selon que le bouton est normalisée, en surbrillance ou désactivée.|  
|[CMFCRibbonButtonsGroup::RemoveAll](../Topic/CMFCRibbonButtonsGroup::RemoveAll.md)|Supprime tous les boutons de l'objet d' `CMFCRibbonButtonsGroup` .|  
|[CMFCRibbonButtonsGroup::SetImages](../Topic/CMFCRibbonButtonsGroup::SetImages.md)|Assigne des images au groupe.|  
|[CMFCRibbonButtonsGroup::SetParentCategory](../Topic/CMFCRibbonButtonsGroup::SetParentCategory.md)|Définit `CMFCRibbonCategory` parent de l'objet d' `CMFCRibbonButtonsGroup` et de tous les boutons qu'il contient \(substitutions [CMFCRibbonBaseElement::SetParentCategory](../Topic/CMFCRibbonBaseElement::SetParentCategory.md).\)|  
  
## Notes  
 Le groupe est dérivé d' [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) et peut être manipulé comme une entité unique.  Vous pouvez positionner le groupe sur un panneau ou menu popup.  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCRibbonButtonsGroup` .  L'exemple montre comment construire un objet d' `CMFCRibbonButtonsGroup`, assigner des images au groupe de boutons de ruban, et ajouter un bouton au groupe de boutons de ruban.  Cet extrait de code fait partie d' [Exemple de client de dessin](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/CPP/cmfcribbonbuttonsgroup-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)  
  
## Configuration requise  
 **En\-tête :** afxribbonbuttonsgroup.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)