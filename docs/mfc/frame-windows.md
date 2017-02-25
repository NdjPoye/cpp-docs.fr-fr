---
title: "Fen&#234;tres frame | Microsoft Docs"
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
  - "CFrameWnd (classe), fenêtres frame"
  - "fenêtres frame de document"
  - "fenêtres frame (C++)"
  - "fenêtres frame (C++), à propos des fenêtres frame"
  - "MDI (C++), fenêtres frame"
  - "MFC (C++), fenêtres frame"
  - "interface monodocument"
  - "interface monodocument, fenêtres frame"
  - "fenêtres fractionnées, et fenêtres frame"
  - "vues (C++), et fenêtres frame"
  - "classes de fenêtre (C++), frame"
  - "fenêtres (C++), MDI"
ms.assetid: 40677339-8135-4f5e-aba6-3fced3078077
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Fen&#234;tres frame
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'une application s'exécute sous Windows, l'utilisateur interagit avec les documents affichés dans les fenêtres cadres.  Une fenêtre cadre de document deux composants principaux : le cadre et le contenu qu'il encadre.  Une fenêtre cadre d'un document peut être une fenêtre cadre d'[interface monodocument](../mfc/sdi-and-mdi.md) \(SDI\) ou une fenêtre enfant d'[interface multidocument](../mfc/sdi-and-mdi.md) \(MDI\).  Windows gère la plupart de l'interaction de l'utilisateur avec la fenêtre cadre : déplacement et redimensionnement la fenêtre, clôture, réduction et agrandissement.  Vous gérez le contenu à l'intérieur du cadre.  
  
## Cadres de fenêtres et vues  
 L'infrastructure MFC utilise les fenêtres de cadre pour contenir des vues.  Les deux composants — cadre et contenu — sont mentionnés et gérés par deux classes différentes de MFC.  Une classe de fenêtre cadre gère le cadre, et une classe d'affichage gère le contenu.  La fenêtre d'affichage est un enfant de la fenêtre cadre.  Le dessin et les autres interventions de l'utilisateur avec le document ont lieu dans la zone client de la vue, et non la zone client de la fenêtre cadre.  La fenêtre cadre fournit un cadre visible autour d'une vue, avec une barre de légende et des contrôles standard tels qu'un menu de contrôle, des boutons pour réduire et agrandir la fenêtre, et des contrôles pour redimensionner la fenêtre.  Le "contenu" inclut la zone client dans la fenêtre, qui est entièrement occupée par une fenêtre enfant — la vue.  L'illustration suivante montre la relation entre les une fenêtre cadre et une vue.  
  
 ![Affichage de la fenêtre Frame](../mfc/media/vc37fx1.png "vc37FX1")  
Fenêtre cadre et vue  
  
## Fenêtres cadres et fenêtres de fractionnement  
 Une autre disposition courante est quand la fenêtre cadre encadre plusieurs vues, généralement en utilisant une [fenêtre fractionnée](../mfc/multiple-document-types-views-and-frame-windows.md).  Dans une fenêtre fractionneé, la zone client de la fenêtre cadre est occupée par une fenêtre fractionnée, qui à son tour a plusieurs fenêtres enfants, appelées les volets, qui sont des vues.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
 **Rubriques générales de fenêtres de cadre**  
  
-   [Objets fenêtres](../mfc/window-objects.md)  
  
-   [Classes de fenêtres de cadre](../mfc/frame-window-classes.md)  
  
-   [Les classes de fenêtre de cadre créées par l'Assistant Application](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [Styles des fenêtres de cadre](../mfc/frame-window-styles-cpp.md)  
  
-   [Ce que font les fenêtres de cadres](../mfc/what-frame-windows-do.md)  
  
 **Rubriques sur l'utilisation de fenêtres de cadres**  
  
-   [Utilisation des fenêtres de cadres](../mfc/using-frame-windows.md)  
  
-   [Création de fenêtres de cadre de document](../mfc/creating-document-frame-windows.md)  
  
-   [Destruction des fenêtres de cadres](../mfc/destroying-frame-windows.md)  
  
-   [Gérer les fenêtres enfants MDI](../mfc/managing-mdi-child-windows.md)  
  
-   [Gérer la vue actuelle](../mfc/managing-the-current-view.md) dans une fenêtre cadre qui contient plusieurs vues  
  
-   [Gestion des menus, barres de contrôle, accélérateurs \(d'autres objets qui partagent l'espace de la fenêtre cadre\)](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
 **Rubriques sur les fonctions spéciales fenêtre de cadre**  
  
-   [Glisser\-déplacer de fichiers](../mfc/dragging-and-dropping-files-in-a-frame-window.md) d'un explorateur ou gestionnaire de fichiers dans une fenêtre cadre  
  
-   [Répondre à un échange dynamique de données \(DDE\)](../mfc/responding-to-dynamic-data-exchange-dde.md)  
  
-   [États Semimodaux : Aide contextuelle Windows \(orchestrant d'autres actions de fenêtre\)](../mfc/orchestrating-other-window-actions.md)  
  
-   [États Semimodaux : impression et aperçu avant impression \(orchestrant d'autres actions de fenêtre\)](../mfc/orchestrating-other-window-actions.md)  
  
 **Rubriques sur les autres types de fenêtres**  
  
-   [Utilisation de vues](../mfc/using-views.md)  
  
-   [Boîtes de dialogue](../mfc/dialog-boxes.md)  
  
-   [des contrôles.](../mfc/controls-mfc.md)  
  
## Voir aussi  
 [Windows](../mfc/windows.md)