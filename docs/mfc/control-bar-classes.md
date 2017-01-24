---
title: "Classes de barre de contr&#244;le | Microsoft Docs"
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
  - "vc.classes.control"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "barres de contrôles, classes"
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de barre de contr&#244;le
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les barres de contrôles sont jointes dans une fenêtre cadre.  Elles contiennent des boutons, des volets d'état, ou des modèles de boîte de dialogue.  Les barres de contrôle en déplacement libre, également appelées palettes d'outils, sont implémentées en les attachant à un objet [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md).  
  
## Barres de contrôles du framework  
 Ces barres de contrôles sont partie intégrante du framework MFC.  Elles sont plus faciles à utilisaer et plus puissantes que les barres de contrôle Windows car elles sont intégrées au framework.  La plupart des applications MFC utilisent ces barres de contrôles plutôt que les barres de contrôle Windows.  
  
 [CControlBar](../mfc/reference/ccontrolbar-class.md)  
 La classe de base pour les barres de contrôles MFC répertoriées dans cette section.  Une barre de contrôle est une fenêtre alignée sur le bord d'une fenêtre cadre.  La barre de contrôle contient soit les contrôles enfants ou les contrôles basés sur des `HWND` ou des contrôles non basés sur `HWND`, tels que les boutons de la barre d'outils.  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 Une barre de contrôles basée sur un modèle de boîte de dialogue.  
  
 [CReBar](../mfc/reference/crebar-class.md)  
 Supporte une barre d'outils qui peut contenir des fenêtres enfant supplémentaires sous forme de contrôles  
  
 [CToolBar](../mfc/reference/ctoolbar-class.md)  
 Le contrôle de barre d'outils qui contient les boutons de commande bitmap non basés sur un `HWND`.  La plupart des applications MFC utilisent cette classe au lieu de `CToolBarCtrl`.  
  
 [CStatusBar](../mfc/reference/cstatusbar-class.md)  
 La classe de base pour les fenêtres de contrôle de la barre d'état.  La plupart des applications MFC utilisent cette classe au lieu de `CStatusBarCtrl`.  
  
## Barres de Contrôle Windows  
 Ces barres de contrôle sont des wrappers légers pour les contrôles Windows correspondants.  Étant donné qu'elles ne sont pas incluses dans le frameworke, il est plus difficile de les utiliser que les barres de contrôle précédemment répertoriées.  La plupart des applications MFC utilisent les barres de contrôle précédemment répertoriées.  
  
 [CRebarCtrl](../mfc/reference/crebarctrl-class.md)  
 Implémente le contrôle interne de l'objet `CRebar`.  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 Une fenêtre horizontale, généralement divisée en volets, où une application peut afficher les informations d'état.  
  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Fournit les fonctionnalités du contrôle commun de barre d'outils Windows.  
  
## Classes liées  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 Une petite fenêtre indépendante qui contient une seule ligne de texte qui décrit l'objectif d'un outil dans une application.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 Gère le stockage permanent des données d'état d'ancrage des barres de contrôle.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)