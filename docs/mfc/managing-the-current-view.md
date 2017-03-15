---
title: "Gestion de l&#39;affichage actuel | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vue active dans une fenêtre frame"
  - "désactiver des vues"
  - "fenêtres frame, affichage actuel"
  - "OnActivateView (méthode)"
  - "vues, activer"
  - "vues, et méthode OnActivateView"
  - "vues, actuels"
  - "vues, désactiver"
ms.assetid: 0a1cc22d-d646-4536-9ad2-3cb6d7092e4a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Gestion de l&#39;affichage actuel
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lors de l'implémentation par défaut des fenêtres frames, une fenêtre cadre contient une vue actuellement active.  Si la fenêtre cadre contient plusieurs vues, comme par exemple dans une fenêtre de fractionnement, la vue actuelle est la vue la plus récente utilisée.  La vue active est indépendante de la fenêtre active windows ou le focus d'entrée actuel.  
  
 Lorsque la vue active change, l'infrastructure notifie la vue actuelle en appelant la fonction membre de [OnActivateView](../Topic/CView::OnActivateView.md).  Déterminez si la vue est activée ou désactivée en examinant le paramètre `bActivate` de `OnActivateView`.  Par défaut, `OnActivateView` définit le focus sur la vue actuelle au moment de l'activation.  Remplacez `OnActivateView` pour effectuer tout traitement spécial lorsque la vue est désactivée ou réactivée.  Par exemple, fournissez des signaux visuels spéciaux pour distinguer la vue active, d'autres vues inactives.  
  
 Une fenêtre cadre transfère les commandes à sa vue actuelle \(active\), comme décrit dans [Routage des commandes](../mfc/command-routing.md), dans le cadre du routage des commandes standard.  
  
## Voir aussi  
 [Utilisation de fenêtres frame](../mfc/using-frame-windows.md)