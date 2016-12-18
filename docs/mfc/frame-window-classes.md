---
title: "Classes de fen&#234;tre frame | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes (C++), fenêtres"
  - "fenêtres frame de document, classes"
  - "classes de fenêtre frame"
  - "classes de fenêtre frame, à propos des classes de fenêtre frame"
  - "MDI (C++), fenêtres frame"
  - "MFC (C++), fenêtres frame"
  - "interface monodocument, fenêtres frame"
  - "classes de fenêtre, frame"
  - "fenêtres (C++), MDI"
ms.assetid: c27e43a7-8ad0-4759-b1b7-43f4725f4132
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de fen&#234;tre frame
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chaque application offre une « frame fenêtre principale, » une fenêtre de bureau qui a généralement le nom d'application dans sa légende.  Chaque document contient généralement un « frame fenêtre de document. » Une fenêtre cadre de document contient au moins une vue, qui présente les données du document.  
  
## Fenêtres cadres dans les applications de SDI et MDI  
 Pour une application de SDI, il existe une fenêtre cadre dérivée de la classe [CFrameWnd](../mfc/reference/cframewnd-class.md).  Cette fenêtre est à la fois la fenêtre principale cadre et la fenêtre cadre de document.  Pour une application MDI, la fenêtre principale cadre est dérivée de la classe [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), et les fenêtres cadres de document, qui sont des fenêtres enfants MDI, sont dérivées de la classe [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md).  
  
## Utiliser la classe frame fenêtre, ou en dériver ?  
 Ces classes fournissent la plupart des fonctionnalités d'affichage cadre dont vous avez besoin pour vos applications.  Dans des conditions normales, le comportement par défaut et l'apparence qu'ils ont conviendront à vos besoins.  Si vous avez besoin de fonctionnalités supplémentaires, dérivez de ces classes.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Classes de fenêtre frame créées par l'Assistant Application](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [Styles des cadres des fenêtres](../mfc/frame-window-styles-cpp.md)  
  
-   [Modification des styles d'une fenêtre créée par MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
## Voir aussi  
 [Fenêtres frame](../mfc/frame-windows.md)