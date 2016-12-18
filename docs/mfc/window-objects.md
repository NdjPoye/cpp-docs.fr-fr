---
title: "Objets fen&#234;tres | Microsoft Docs"
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
  - "fenêtres frame (C++), C++ (objets fenêtres)"
  - "HWND"
  - "HWND, objets fenêtres"
  - "messages (C++), Windows"
  - "MFC (C++), fenêtres"
  - "objets (C++), fenêtres"
  - "Visual C++, objets fenêtres"
  - "messages de fenêtre (C++)"
  - "objets fenêtres (C++)"
  - "fenêtres (C++), C++ (objets fenêtres)"
  - "fenêtre Windows (C++)"
ms.assetid: 28b33ce2-af05-4617-9d03-1cb9a02be687
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Objets fen&#234;tres
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC fournit la classe [CWnd](../mfc/reference/cwnd-class.md) pour encapsuler la poignée d' `HWND` d'une fenêtre.  L'objet d' `CWnd` est un objet de Windows de C\+\+, séparé d' `HWND` qui représente une fenêtre Windows mais qui le contient.  Utilisez `CWnd` pour dériver vos classes de la fenêtre enfant, ou utilisez l'une des nombreuses classes de MFC dérivées d' `CWnd`.  La classe `CWnd` est la classe de base pour toutes les fenêtres, en particulier les cadres de fenêtres, les boîtes de dialogue, les fenêtres enfants, les contrôles et les barres de contrôles telles que les barres d'outils.  Une bonne compréhension d' [la relation entre un objet de fenêtre de C\+\+ et un HWND](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md) est cruciale pour la programmation efficace avec MFC.  
  
 MFC fournit certaines fonctionnalités et gestion par défaut des fenêtres, mais vous pouvez dériver votre propre classe à partir d' `CWnd` et utiliser ses fonctions membre pour personnaliser les fonctionnalités fournies.  Vous pouvez créer des fenêtres enfants en construisant un objet d' `CWnd` et en appelant la fonction membre d' [Créer](../Topic/CWnd::Create.md), puis personnaliser les fenêtres enfants à l'aide de fonctions membres d' `CWnd`.  Vous pouvez inclure des objets dérivés d' [CView](../mfc/reference/cview-class.md), tels que des vues formulaire ou des arborescences, dans une cadre de fenêtre.  Et vous pouvez prendre en charge plusieurs vues de vos documents via des volets de séparateur, fournis par la classe [CSplitterWnd](../mfc/reference/csplitterwnd-class.md).  
  
 Chaque objet dérivé de la classe `CWnd` contient une table de messages, dans laquelle vous pouvez mapper des messages Windows ou des ID de commandee à vos propres gestionnaires.  
  
 La documentation générale sur la programmation pour Windows constitue une bonne ressource pour apprendre à utiliser les fonctions membres d' `CWnd`, qui encapsulent les API d' `HWND`.  
  
## Fonctions pour Exécuter sur un CWnd  
 `CWnd` et ses [classes dérivées de fenêtres](../mfc/derived-window-classes.md) fournissent des constructeurs, des destructeurs et des fonctions membre pour initialiser l'objet, créent des structures sous\-jacentes Windows, et accèdent au `HWND`encapsulé.  `CWnd` fournit également des fonctions membres qui encapsulent les API Windows pour envoyer des messages, accéder à l'état de la fenêtre, convertir les coordonnées, mettre à jour, défiler, accéder au Presse\-papiers et de nombreuses autres tâches.  La plupart des API de gestion de fenêtre Windows qui prennent un argument d' `HWND` sont incluses comme fonctions membres d' `CWnd`.  Les noms des fonctions et leurs paramètres sont conservés dans la fonction membre d' `CWnd`.  Pour plus d'informations sur les API Windows encapsulés par `CWnd`, consultez la classe [CWnd](../mfc/reference/cwnd-class.md).  
  
## CWnd et Messages Windows  
 Un des objectifs premiers d' `CWnd` est de fournir une interface pour gérer les messages Windows, tels qu' `WM_PAINT` ou `WM_MOUSEMOVE`.  Plusieurs fonctions membres d' `CWnd` sont des gestionnaires de messages standard — ceux commençant avec l'identificateur **afx\_msg** et le préfixe « Sur, » comme `OnPaint` et **OnMouseMove**.  [Gestion des messages et mappage](../mfc/message-handling-and-mapping.md) couvre les messages et la gestion des messages en détail.  Les informations s'appliquent identiquement aux fenêtres de l'infrastructure et celles que vous créez vous\-même à des fins spéciales.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [La relation entre un objet de fenêtre C\+\+ et un HWND](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)  
  
-   [Classes de fenêtre dérivées](../mfc/derived-window-classes.md)  
  
-   [Création de fenêtres](../mfc/creating-windows.md)  
  
-   [Destruction d'objets fenêtres](../mfc/destroying-window-objects.md)  
  
-   [Détachement d'un objet CWnd de son HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [Utilisation d'objets fenêtres](../mfc/working-with-window-objects.md)  
  
-   [Contexte de périphérique](../mfc/device-contexts.md): objets qui rendent l'outil de dessin Windows indépendant.  
  
-   [Objets graphiques](../mfc/graphic-objects.md): stylets, pinceaux, les polices, bitmap, palettes, régions  
  
## Voir aussi  
 [Windows](../mfc/windows.md)