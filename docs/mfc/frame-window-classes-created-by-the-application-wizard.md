---
title: "Classes de fen&#234;tre frame cr&#233;&#233;es par l&#39;Assistant Application | Microsoft Docs"
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
  - "CMainFrame"
  - "CMainFrame::PreCreateWindow"
  - "CMainFrame.PreCreateWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistants Application (C++), classes de fenêtre frame créées par"
  - "CFrameWnd (classe), fenêtres frame"
  - "classes (C++), fenêtre frame"
  - "CMainFrame (classe)"
  - "CMDIChildWnd (classe), fenêtres frame"
  - "CMDIFrameWnd (classe), fenêtres frame"
  - "classes de fenêtre frame, créées par les Assistants Application"
  - "classes de fenêtre"
  - "classes de fenêtre, frame"
ms.assetid: 9947df73-4470-49a0-ac61-7b6ee401a74e
caps.latest.revision: 8
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de fen&#234;tre frame cr&#233;&#233;es par l&#39;Assistant Application
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous utilisez [L'Application](../ide/creating-desktop-projects-by-using-application-wizards.md) pour créer une application squelette, en plus de l'application, du document, les classes d'affichage, l'Application crée une classe de fenêtre dérivée cadre de la fenêtre principale cadre de votre application.  La classe est appelée `CMainFrame` par défaut, les fichiers qui contiennent le sont appelés MAINFRM.H et MAINFRM.CPP.  
  
 Si votre application est SDI, votre classe de `CMainFrame` est dérivée de la classe [CFrameWnd](../mfc/reference/cframewnd-class.md).  
  
 Si votre application est MDI, `CMainFrame` est dérivé de la classe [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md).  Dans ce cas `CMainFrame` implémente le cadre principal, qui contient le menu, la barre d'outils, et les barres d'état.  L'application assistance ne dérive pas de nouveaux documents de classe fenêtre\-cadre pour vous.  Au lieu de cela, il utilise l'implémentation par défaut dans [Classe de CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md).  L'infrastructure MFC crée une fenêtre enfant pour contenir chaque vue \(qui peut être de type `CScrollView`, `CEditView`, `CTreeView`, `CListView`, etc.\) que l'application requiert.  Si vous devez personnaliser le cadre de fenêtre de document, créez une nouvelle classe cadre de fenêtre de document \(voir le [Ajouter une classe](../ide/adding-a-class-visual-cpp.md)\).  
  
 Si vous choisissez de prendre en charge une barre d'outils, la classe contient également des variables membres de type [CToolBar](../mfc/reference/ctoolbar-class.md) et [CStatusBar](../mfc/reference/cstatusbar-class.md) et une fonction gestionnaire des messages de `OnCreate` pour initialiser deux [barres de contrôle](../mfc/control-bars.md).  
  
 Ces classes fenêtre\-cadre marche comme tel, mais pour améliorer leur fonctionnalité, vous devez ajouter des variables membres et les fonctions de membre.  Vous pouvez également souhaiter avoir votre classe fenêtre gérer d'autres messages de Windows.  Pour plus d'informations, consultez [Modification des styles d'une fenêtre créée par MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md).  
  
## Voir aussi  
 [Classes de fenêtre frame](../mfc/frame-window-classes.md)   
 [Fichiers d'en\-tête et fichiers sources de contrôle ou de programme MFC](../ide/mfc-program-or-control-source-and-header-files.md)