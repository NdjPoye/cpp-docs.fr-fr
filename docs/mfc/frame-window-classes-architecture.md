---
title: "Classes de fen&#234;tre frame (architecture) | Microsoft Docs"
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
  - "classes de fenêtre frame, architecture document/vue"
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Classes de fen&#234;tre frame (architecture)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans l'architecture documents\/Vue, windows cadres sont des fenêtres qui contiennent une fenêtre d'affichage.  Elles prennent en charge également comporter des barres de contrôles jointes à celles\-ci.  
  
 Dans les applications \(MDI\) de l'interface MD, la fenêtre principale est dérivée de `CMDIFrameWnd`.  Il contient tous les cadres des documents, qui sont des objets `CMDIChildWnd`.  Les objets `CMDIChildWnd` , à leur tour, contiennent les vues de documents.  
  
 Dans les applications \(SDI\) de l'interface monodocument, la fenêtre principale, dérivée de `CFrameWnd`, contient la vue du document actif.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 La classe de base pour la fenêtre principale cadre d'une application de SDI.  Également la classe de base pour une autre fenêtre cadre classe.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 La classe de base pour la fenêtre principale cadre d'une application de MDI.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 La classe de base pour les autres cadres de document d'une application MDI.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Fournit la fenêtre cadre d'une vue lorsqu'un document serveur est modifié en place.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)