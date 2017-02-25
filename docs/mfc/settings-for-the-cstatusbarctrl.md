---
title: "Param&#232;tres de l&#39;objet CStatusBarCtrl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl (classe), paramètres"
  - "contrôles de barre d'état, paramètres"
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Param&#232;tres de l&#39;objet CStatusBarCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La position par défaut d'une fenêtre d'état[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) est sur le bas de la fenêtre parente, mais vous pouvez spécifier le style `CCS_TOP` pour le faire apparaître en haut de la zone client de la fenêtre parente.  
  
 Vous pouvez spécifier au style **SBARS\_SIZEGRIP** d'inclure une poignée de dimensionnement à l'extrémité droite de la fenêtre d'état `CStatusBarCtrl`.  Une poignée de dimensionnement est semblable à une bordure de dimensionnement ; il s'agit d'une zone rectangulaire que l'utilisateur peut cliquer et faire glisser pour redimensionner la fenêtre parente.  
  
> [!NOTE]
>  Si vous combinez `CCS_TOP` et les styles de **SBARS\_SIZEGRIP**, la poignée de dimensionnement résultante ne fonctionne pas même si la système dessine dans la fenêtre d'état.  
  
 La procédure d'affichage de la fenêtre d'état définit automatiquement la taille et la position initiales de la fenêtre de contrôle.  La largeur est le même que celle de la zone client de la fenêtre parente.  La hauteur est basée sur la taille de la police actuellement sélectionnée dans le contexte du périphérique de la fenêtre d'état et sur la largeur des bordures de fenêtre.  
  
 La procédure d'affichage règle automatiquement la taille de la fenêtre d'état lorsqu'elle reçoit un message `WM_SIZE`.  En règle générale, lorsque la taille de la fenêtre parente change, le parent envoie un message `WM_SIZE` dans la fenêtre d'état.  
  
 Vous pouvez définir la hauteur minimale de la zone de dessin représentant une fenêtre d'état en appelant [SetMinHeight](../Topic/CStatusBarCtrl::SetMinHeight.md), en spécifiant la hauteur minimale en pixels.  La zone de dessin ne comprend pas les bordures de la fenêtre.  
  
 Vous récupérez la largeur des bordures d'état en appelant [GetBorders](../Topic/CStatusBarCtrl::GetBorders.md).  Cette fonction membre inclut le pointeur vers un tableau de trois élément qui reçoit la largeur de la bordure horizontale, la bordure verticale, et la bordure entre les rectangles.  
  
## Voir aussi  
 [Utilisation de CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)