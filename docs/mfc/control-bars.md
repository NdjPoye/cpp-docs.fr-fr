---
title: "Barres de contr&#244;les | Microsoft Docs"
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
  - "CControlBar (classe), barres de contrôles MFC"
  - "CDialogBar (classe), barres de contrôles"
  - "Barres de commandes, types de"
  - "barres de contrôles (C++)"
  - "barres de contrôles (C++), types de"
  - "CStatusBar (classe), barres de contrôles"
  - "CToolBar (classe), barres de contrôles"
  - "barres de boîte de dialogue, barres de contrôles"
  - "MFC, barres de contrôles"
  - "barres d'état, barres de contrôles"
  - "barres d'outils (C++), barres de contrôles"
ms.assetid: 31831910-3d23-4d70-9e71-03cc02f01ec4
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Barres de contr&#244;les
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

« La barre de contrôle » est le nom général pour les barres d'outils, les barres d'état, et les barres de boîtes de dialogue.  Les classes MFC `CToolBar`, `CStatusBar`, `CDialogBar`, `COleResizeBar`, et **CReBar** dérivent de la classe [CControlBar](../mfc/reference/ccontrolbar-class.md), qui implémente leurs fonctionnalités communes.  
  
 Les barres de contrôles sont des fenêtres affichant des lignes de contrôles avec lesquelles les utilisateurs peuvent sélectionner les options, l'exécution de commandes, ou obtenir des informations du programme.  Les types de barres de contrôles comprennent des barres d'outils, les barres de boîtes de dialogue, les barres d'état.  
  
-   Les barres d'outils, dans la classe [CToolBar](../mfc/reference/ctoolbar-class.md)  
  
-   Les barres d'état, dans la classe [CStatusBar](../mfc/reference/cstatusbar-class.md)  
  
-   Les barres de la boîte de dialogue, dans la classe [CDialogBar](../mfc/reference/cdialogbar-class.md)  
  
-   Rebars, dans la classe [CReBar](../mfc/reference/crebar-class.md)  
  
> [!IMPORTANT]
>  À compter de la version 4,0 de MFC, les barres d'outils, les barres d'état, et les info\-bulles sont implémentées à l'aide de la fonction système implémentée dans le comctl32.dll au lieu de détail précédent d'implémentation de MFC.  Dans la version 6,0 de MFC, **CReBar**, qui inclut également des fonctionnalités de comctl32.dll, a été ajouté.  
  
 Les brèves introductions aux types de barre de contrôle suivent.  Pour plus d'informations, consultez les liens ci\-dessous.  
  
## Barres de contrôles  
 Les barres de contrôles améliorent considérablement l'utilisation d'un programme en fournissant des actions rapides et des actions de commande d'une étape.  La classe `CControlBar` fournit les fonctionnalités communes de toutes les barres d'outils, barres d'état, et barres de la boîte de dialogue.  `CControlBar` fournit des fonctionnalités pour positionner la barre de contrôles dans la fenêtre parente cadre.  Étant donné qu'une barre de contrôle est généralement une fenêtre enfant d'une fenêtre parente frame, il s'agit d'un « frère » à la vue du client ou du client MDI de la fenêtre cadre.  Un objet de barre de contrôle utilise des informations sur son rectangle client de la fenêtre parente pour se positionner.  Il modifie le reste du rectangle de la fenêtre du client parent afin que la vue du client ou la fenêtre du client MDI cliente remplisse le reste de la fenêtre du client.  
  
> [!NOTE]
>  Si un bouton de la barre de contrôle n'a pas **COMMANDE** ou un gestionnaire d' **UPDATE\_COMMAND\_UI**, l'infrastructure désactive automatiquement le bouton.  
  
## Barres d'outils  
 Une barre d'outils est une barre de contrôle qui affiche une ligne de boutons bitmap qui exécutent des commandes.  Appuyer sur un bouton de la barre d'outils est équivalent à choisir un élément de menu ; il appelle le même gestionnaire mappé à un élément de menu si cet élément de menu a le même ID que le bouton de la barre d'outils.  Les boutons peuvent être configurés pour apparaitre et se comporter comme des boutons poussoir, boutons de radio, ou cases à cocher.  Une barre d'outils est généralement alignée au haut d'un cadre de fenêtre, mais une barre d'outils de MFC pouvez « se garer » à n'importe quel côté de la fenêtre ou flotter dans sa propre fenêtre de mini cadre.  Une barre d'outils peut également « flotter » et vous pouvez modifier sa taille et la faire glisser avec une souris.  Une barre d'outils peut également afficher des info\-bulles lorsque l'utilisateur bouge la souris sur les boutons de la barre d'outils.  Une info\-bulle est une fenêtre contextuelle minuscule qui décrit brièvement l'objectif du bouton.  
  
> [!NOTE]
>  À compter de la version 4.0 de MFC, la classe [CToolBar](../mfc/reference/ctoolbar-class.md) utilise le contrôle courant de barre d'outils Windows.  Un `CToolBar` contient [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md).  Les barres d'outils anciennes sont encore prises en charge, toutefois.  Consultez l'article [Barres d'outils](../mfc/mfc-toolbar-implementation.md).  
  
## Barres d'état  
 Une barre d'état est une barre de contrôle qui contient les volets de texte OUTPUT, ou « indicateurs. » Les volets de sortie sont fréquemment utilisés comme des lignes de message et comme indicateurs de états.  Les exemples de messages incluent les lignes d'aide\- message de commande qui expliquent brièvement le menu ou la commande sélectionné de la barre d'outils du volet situé à l'extrême gauche de la barre d'état par défaut créée par l'Application MFC.  Les exemples KPI inclut le ARRÊT DÉFIL, le VERROUILLAGE NUMERIC, et d'autres clés.  Les barres d'état sont généralement alignées en bas de la fenêtre cadre.  Consultez la classe [CStatusBar](../mfc/reference/cstatusbar-class.md) et [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)classe.  
  
## Barres de boîte de dialogue  
 Une barre de la boîte de dialogue est une barre de contrôle, sur une ressource modèle de la boîte de dialogue, avec la fonctionnalité d'une boîte de dialogue non modales.  Les barres de la boîte de dialogue peuvent contenir des fenêtres, la valeur personnalisée, ou les contrôles ActiveX.  Comme dans une boîte de dialogue, l'utilisateur peut se déplacer dans les contrôles.  Les barres de la boîte de dialogue peuvent être alignées dans la partie supérieure, inférieure, gauche, ou le côté droit d'un cadre de fenêtre et elles peuvent également être flottés dans leur propre cadre de fenêtre.  Consultez la classe [CDialogBar](../mfc/reference/cdialogbar-class.md).  
  
## Rebars  
 Un [rebar](../mfc/using-crebarctrl.md) est une barre de contrôle qui fournit des informations de disposition, de persistance et d'état pour les contrôles rebar.  Objet rebar peut contenir plusieurs fenêtres enfants, généralement d'autres contrôles, notamment les zones d'édition, des barres d'outils, les zones de liste.  Objet rebar peut afficher les fenêtres enfants sur une bitmap spécifiée.  Vous pouvez redimensionner automatiquement ou manuellement en cliquant sur ou en faisant glisser la barre vers pinces.  Consultez la classe [CReBar](../mfc/reference/crebar-class.md).  
  
## Voir aussi  
 [Éléments de l'interface utilisateur](../mfc/user-interface-elements-mfc.md)