---
title: "Classes de fen&#234;tre frame (Fen&#234;tres) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.frame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes de fenêtre frame, référence"
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Classes de fen&#234;tre frame (Fen&#234;tres)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fenêtres cadres sont des fenêtres qui encadrent une application ou une partie d'une application.  Les fenêtres cadres contiennent généralement d'autres fenêtres, telles que les vues, les barres d'outils, et les barres d'état.  Dans le cas de `CMDIFrameWnd`, elles peuvent contenir des objets `CMDIChildWnd` indirectement.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 La classe de base pour la fenêtre principale cadre d'une application de SDI.  Également la classe de base pour une autre fenêtre cadre classe.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 La classe de base pour la fenêtre principale cadre d'une application de MDI.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 La classe de base pour les autres cadres de document d'une application MDI.  
  
 [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md)  
 Une fenêtre frame de demi\-hauteur généralement visible autour de barres d'outils flottantes.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Fournit la fenêtre cadre d'une vue lorsqu'un document serveur est modifié en place.  
  
## Classe reliée  
 La classe `CMenu` fournit une interface à laquelle accéder aux menus de votre application.  Il est utile pour manipuler des menus dynamiquement pendant l'exécution ; par exemple, en ajoutant ou en supprimant des éléments de menu en fonction de le contexte.  Bien que les menus sont le plus souvent utilisés avec windows frames, ils peuvent également être utilisés avec des boîtes de dialogue et d'autres fenêtres de nonchild.  
  
 [CMenu](../mfc/reference/cmenu-class.md)  
 Encapsule une gestion `HMENU` dans la barre de menus et les menus contextuels de l'application.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)