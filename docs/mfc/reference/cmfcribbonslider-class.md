---
title: "CMFCRibbonSlider Class | Microsoft Docs"
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
  - "CMFCRibbonSlider"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonSlider class"
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
caps.latest.revision: 43
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonSlider Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCRibbonSlider` implémente un contrôle Slider que vous pouvez ajouter une barre de ruban ou une barre d'état du ruban.  Le contrôle Slider de ruban ressemble aux curseurs de zoom qui apparaissent dans les applications Office 2007.  
  
## Syntaxe  
  
```  
class CMFCRibbonSlider : public CMFCRibbonBaseElement  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonSlider::CMFCRibbonSlider](../Topic/CMFCRibbonSlider::CMFCRibbonSlider.md)|Les éléments et initialise un contrôle Slider de ruban.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonSlider::GetPos](../Topic/CMFCRibbonSlider::GetPos.md)|Retourne la position actuelle du contrôle Slider.|  
|[CMFCRibbonSlider::GetRangeMax](../Topic/CMFCRibbonSlider::GetRangeMax.md)|Retourne la valeur maximale du curseur.|  
|[CMFCRibbonSlider::GetRangeMin](../Topic/CMFCRibbonSlider::GetRangeMin.md)|Retourne la valeur minimale du curseur.|  
|[CMFCRibbonSlider::GetRegularSize](../Topic/CMFCRibbonSlider::GetRegularSize.md)|Retourne la taille normale de l'élément ruban.  \(Substitutions [CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md).\)|  
|[CMFCRibbonSlider::GetZoomIncrement](../Topic/CMFCRibbonSlider::GetZoomIncrement.md)|Retourne la taille de l'index de zoom du contrôle Slider.|  
|[CMFCRibbonSlider::HasZoomButtons](../Topic/CMFCRibbonSlider::HasZoomButtons.md)|Spécifie si le curseur a des boutons de zoom.|  
|[CMFCRibbonSlider::OnDraw](../Topic/CMFCRibbonSlider::OnDraw.md)|Appelé par l'infrastructure pour dessiner l'élément ruban.  \(Substitutions [CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md).\)|  
|[CMFCRibbonSlider::SetPos](../Topic/CMFCRibbonSlider::SetPos.md)|Définit la position actuelle du contrôle Slider.|  
|[CMFCRibbonSlider::SetRange](../Topic/CMFCRibbonSlider::SetRange.md)|Spécifie la plage du contrôle Slider en définissant les valeurs minimales et maximales.|  
|[CMFCRibbonSlider::SetZoomButtons](../Topic/CMFCRibbonSlider::SetZoomButtons.md)|Affiche ou masque les boutons de zoom.|  
|[CMFCRibbonSlider::SetZoomIncrement](../Topic/CMFCRibbonSlider::SetZoomIncrement.md)|Taille des jeux de l'index de zoom du contrôle Slider.|  
  
## Notes  
 Vous pouvez utiliser la méthode d' `SetRange` pour configurer la plage d'index de zoom du curseur.  Vous pouvez définir la position actuelle du curseur à l'aide de la méthode d' `SetPos` .  
  
 Vous pouvez afficher les boutons circulaires de zoom à gauche et droit du contrôle Slider à l'aide de la méthode d' `SetZoomButtons` .  Par défaut, le curseur est horizontal, le bouton gauche de zoom affiche un signe moins et le bouton droit de zoom affiche un signe plus.  
  
 La méthode d' `SetZoomIncrement` définit l'index pour ajouter la valeur ou soustraire de la position actuelle lorsqu'un utilisateur clique sur les boutons de zoom.  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCRibbonSlider` pour définir les propriétés du curseur.  L'exemple montre comment construire un objet d' `CMFCRibbonSlider` , afficher des boutons de zoom, définir la position actuelle du contrôle Slider, et définir la plage de valeurs pour le contrôle Slider.  
  
 [!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/CPP/cmfcribbonslider-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)  
  
## Configuration requise  
 **en\-tête :** afxribbonslider.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)