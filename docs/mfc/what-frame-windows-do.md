---
title: "Fonctionnement des fen&#234;tres frame | Microsoft Docs"
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
  - "fenêtres frame, à propos des fenêtres frame"
  - "fenêtres frame, tâches"
  - "MFC, fenêtres frame"
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Fonctionnement des fen&#234;tres frame
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En plus d'encadrer simplement une vue, les fenêtres de cadre sont responsables de nombreuses tâches impliquées dans coordination du cadre avec sa vue et l'application.  [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) et [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) héritent de [CFrameWnd](../mfc/reference/cframewnd-class.md), elles ont les fonctions `CFrameWnd` ainsi que les nouvelles fonctions qu'ils ajoutent.  Les exemples de fenêtres enfants contiennent des vues et contrôles, tels que les boutons et zones de liste, et barres de contrôle, y compris les barres d'outils, les barres d'état, et les barres de la boîte de dialogue.  
  
 La fenêtre cadre est chargée de gérer la disposition de ses fenêtres enfants.  Dans le framework MFC, une fenêtre cadre positionne toutes les barres de contrôle, des vues, et d'autres fenêtres enfants à l'intérieur de la zone client.  
  
 La fenêtre cadre transfère également les commandes ses vues et peut répondre aux messages de notification des fenêtres de contrôle.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Barres de contrôle \(comment elles s'insèrent dans la fenêtre cadre\)](../mfc/control-bars.md)  
  
-   [Gestion des menus, barres de contrôle, accélérateurs \(comment ils s'insèrent dans la fenêtre cadre\)](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [Routage des commandes \(de la fenêtre cadre à sa vue et autres cibles de la commande\)](../mfc/command-routing.md)  
  
-   [Architecture document\/vue](../mfc/document-view-architecture.md)  
  
-   [Control bars](../mfc/control-bars.md)  
  
-   [des contrôles.](../mfc/controls-mfc.md)  
  
## Voir aussi  
 [Fenêtres frame](../mfc/frame-windows.md)