---
title: "Classes de fen&#234;tre d&#233;riv&#233;es | Microsoft Docs"
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
  - "classes (C++), dérivés"
  - "CWnd (classe), classes dérivées de"
  - "classes dérivées, classes de fenêtre"
  - "hiérarchies, classes de fenêtre"
  - "hiérarchie de classe de fenêtre"
  - "classes de fenêtre, dérivés"
ms.assetid: 6f7e437e-fbde-4a06-bfab-72d9dbf05292
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de fen&#234;tre d&#233;riv&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez créer des fenêtres directement depuis [CWnd](../mfc/reference/cwnd-class.md), ou dériver de nouvelles classes de fenêtres depuis `CWnd`.  Voici comment vous créez généralement vos propres fenêtres personnalisées.  Toutefois, la plupart des fenêtres utilisées dans un programme .NET Framework sont plutôt créées à partir d'une des classes `CWnd` de cadre de fenêtre dérivées fournies par MFC.  
  
## Classes de fenêtre frame  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 Utilisé pour les fenêtres frame SDI qui encadrent un document unique et sa vue.  La fenêtre frame est à la fois la fenêtre frame principale pour l'application et la fenêtre frame du document actif.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 Utilisé comme fenêtre frame principale pour les applications MDI.  La fenêtre frame principale est un conteneur pour toutes les fenêtres de document MDI et partage sa barre de menus avec elles.  Une fenêtre frame MDI est une fenêtre de niveau supérieur qui apparaît sur le Bureau.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 Utilisé pour des documents individuels que vous avez ouvert dans une fenêtre frame principale MDI.  Chaque document et sa vue sont encadrés par une fenêtre frame MDI enfant contenue dans la fenêtre frame principale MDI.  Une fenêtre enfant MDI ressemble beaucoup à une fenêtre frame classique mais est contenue dans une fenêtre frame MDI au lieu de reposer sur le Bureau.  Toutefois, il manque à la fenêtre enfant MDI une barre de menus qui lui est propre et elle doit partager la barre de menus de la fenêtre frame MDI qui la contient.  
  
 Pour plus d'informations, consultez [Fenêtres Frame](../mfc/frame-windows.md).  
  
## D'autres classes de fenêtres dérivées de CWnd  
 En plus des fenêtres frames, plusieurs autres grandes catégories de fenêtres sont dérivés de `CWnd`:  
  
 *Vues*  
 Les vues sont créées à l'aide de la classe `CWnd` dérivée [CView](../mfc/reference/cview-class.md) \(ou une de ses classes dérivées\).  Une vue est attachée à un document et sert d'intermédiaire entre le document et l'utilisateur.  Une vue est une fenêtre enfant \(pas un enfant MDI\) qui remplit généralement la zone cliente d'une fenêtre frame SDI ou d'une fenêtre frame enfant MDI \(ou cette partie de la zone cliente non couverte par une barre d'outils et\/ou une barre d'état\).  
  
 *Boîtes de dialogue*  
 Les boîtes de dialogue sont créées avec une classe `CWnd`dérivée [CDialog](../mfc/reference/cdialog-class.md).  
  
 *Formulaires*  
 Les vues formulaires reposant sur des ressources de modèles de dialogue, telles que les boîtes de dialogue, sont créés à l'aide des classes [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), ou [CDaoRecordView](../mfc/reference/cdaorecordview-class.md).  
  
 *Contrôles*  
 Les contrôles tels que les boutons, les zones de liste et les zones de liste modifiables sont créés à l'aide d'autres classes dérivées de `CWnd`.  Consultez [Rubriques de contrôle](../mfc/controls-mfc.md).  
  
 *Barres de contrôles*  
 Fenêtres enfants contenant des contrôles.  Les exemples incluent des barres d'outils et des barres d'état.  Consultez [Barres de contrôles](../mfc/control-bars.md).  
  
## Hiérarchie de classe de fenêtre  
 Se renvoyer à [Graphique de hiérarchie MFC](../mfc/hierarchy-chart.md) dans la *référence MFC*.  Les vues sont expliquées dans [Architecture Document\/Vue](../mfc/document-view-architecture.md).  Les boîtes de dialogue sont expliquées dans [Boîtes de dialogue](../mfc/dialog-boxes.md).  
  
## Création de vos propres classes de fenêtres spécialisés  
 En plus des classes de fenêtres fournies par la bibliothèque de classes, vous pouvez avoir besoin de fenêtres enfants spécialisés.  Pour créer une telle fenêtre, créer votre propre classe dérivée de [CWnd](../mfc/reference/cwnd-class.md)et faites en une fenêtre enfant d'une frame ou d'une vue.  Gardez à l'esprit que la structure gère l'étendue de la zone cliente d'une fenêtre frame de document.  L'essentiel de la zone cliente est gérée par une vue, mais d'autres fenêtres, telles que des barres de contrôles ou vos propres fenêtres personnalisées, peuvent partager l'espace avec la vue.  Vous devrez peut\-être interagir avec les mécanismes dans les classes [CView](../mfc/reference/cview-class.md) et [CControlBar](../mfc/reference/ccontrolbar-class.md) pour positionner les fenêtres enfants dans la zone cliente d'une fenêtre frame.  
  
 [Création des fenêtres](../mfc/creating-windows.md) décrit la création d'objets fenêtre et les fenêtres qu'ils gèrent.  
  
## Voir aussi  
 [Objets fenêtres](../mfc/window-objects.md)