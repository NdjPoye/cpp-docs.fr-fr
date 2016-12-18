---
title: "CMFCCaptionButton Class | Microsoft Docs"
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
  - "CMFCCaptionButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCaptionButton class"
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
caps.latest.revision: 28
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCCaptionButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCCaptionButton` implémente un bouton qui s'affiche dans la barre de légende pour un volet d'ancrage ou une fenêtre mini\-frame.  En général, l'infrastructure crée des boutons de légende automatiquement.  
  
## Syntaxe  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## Membres  
  
### Constructeurs  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCCaptionButton::CMFCCaptionButton](../Topic/CMFCCaptionButton::CMFCCaptionButton.md)|Crée un objet de CMFCCaptionButton.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCCaptionButton::GetHit](../Topic/CMFCCaptionButton::GetHit.md)|Retourne la commande représentée par le bouton.|  
|[CMFCCaptionButton::GetIconID](../Topic/CMFCCaptionButton::GetIconID.md)|Retourne l'ID d'image associé à le bouton.|  
|[CMFCCaptionButton::GetRect](../Topic/CMFCCaptionButton::GetRect.md)|Retourne le rectangle occupé par le bouton.|  
|[CMFCCaptionButton::GetSize](../Topic/CMFCCaptionButton::GetSize.md)|Retourne la largeur et la hauteur du bouton.|  
|[CMFCCaptionButton::IsMiniFrameButton](../Topic/CMFCCaptionButton::IsMiniFrameButton.md)|Indique si la hauteur de la barre de titre est définie à la taille mini.|  
|[CMFCCaptionButton::Move](../Topic/CMFCCaptionButton::Move.md)|Définit l'état de l'emplacement de dessin du bouton et show de fenêtre.|  
|[CMFCCaptionButton::OnDraw](../Topic/CMFCCaptionButton::OnDraw.md)|Dessine le bouton de légende.|  
|[CMFCCaptionButton::SetMiniFrameButton](../Topic/CMFCCaptionButton::SetMiniFrameButton.md)|Définit la mini taille de la barre de titre.|  
  
## Notes  
 Vous pouvez dériver une classe de [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md) et utiliser la méthode protégée, `AddButton`, pour ajouter des boutons de légende à un mini fenêtre frame.  
  
 CPaneFrameWnd.h définit les ID de commande pour deux types de boutons de légende :  
  
-   `AFX_CAPTION_BTN_PIN`, qui affiche un bouton d'épingle lorsque le prend en charge du volet d'ancrage masquer automatiquement le mode.  
  
-   `AFX_CAPTION_BTN_CLOSE`, qui affiche un bouton **Fermer** lorsque le volet peut être fermé ou masqué.  
  
## Exemple  
 L'exemple suivant montre comment construire un objet d' `CMFCCaptionButton` et mini définir la taille de la barre de titre.  
  
 [!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/CPP/cmfccaptionbutton-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)  
  
## Configuration requise  
 **en\-tête :** afxcaptionbutton.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)