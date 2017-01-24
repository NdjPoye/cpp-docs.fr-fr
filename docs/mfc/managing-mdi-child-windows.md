---
title: "G&#233;rer les fen&#234;tres enfants MDI | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MDICLIENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fenêtres enfants"
  - "fenêtres enfants, et fenêtre MDICLIENT"
  - "fenêtres frame (C++), fenêtres enfants MDI"
  - "MDI (C++), fenêtres enfants"
  - "MDI (C++), fenêtres frame"
  - "fenêtre MDICLIENT"
  - "fenêtres (C++), MDI"
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# G&#233;rer les fen&#234;tres enfants MDI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fenêtres cadres principales MDI \(une par application\) contiennent une fenêtre enfant spéciale appelée la fenêtre **MDICLIENT**.  La fenêtre **MDICLIENT** gère la zone client de la fenêtre cadre principale, et elle\-même a des fenêtres enfants : les fenêtres de document, dérivées de `CMDIChildWnd`.  Les fenêtres de document sont les fenêtres cadres elles\-mêmes \(les fenêtres enfants MDI\), elles peuvent également avoir leurs propres enfants.  Dans tous ces cas, la fenêtre parente gère ses fenêtres enfants et transfère des commandes associées.  
  
 Dans une fenêtre cadre MDI, la fenêtre cadre gère la fenêtre de **MDICLIENT**, la replaçant conjointement avec les barres de contrôle.  La fenêtre de **MDICLIENT**, à son tour, gère toutes les fenêtres enfants MDI cadre.  L'illustration suivante montre la relation entre un point cadre MDI, sa fenêtre **MDICLIENT**, et ses fenêtres cadres de document enfants.  
  
 ![Fenêtres enfants dans une fenêtre frame MDI](../mfc/media/vc37gb1.png "vc37GB1")  
Fenêtres cadres MDI et enfants  
  
 Une fenêtre cadre MDI fonctionne aussi conjointement avec la fenêtre enfant MDI active, s'il en existe une.  La fenêtre cadre MDI délègue des messages de commande à l'enfant MDI avant qu'il essaye de les gérer lui même.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Création de fenêtres cadre de document](../mfc/creating-document-frame-windows.md)  
  
-   [Styles de fenêtre cadre](../mfc/frame-window-styles-cpp.md)  
  
## Voir aussi  
 [Utilisation de fenêtres frame](../mfc/using-frame-windows.md)