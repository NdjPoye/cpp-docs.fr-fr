---
title: "Impl&#233;mentation de la barre d&#39;&#233;tat dans MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COldStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COldStatusBar (classe)"
  - "CStatusBar (classe), et classe CStatusBarCtrl"
  - "CStatusBar (classe), et barres d'état MFC"
  - "CStatusBarCtrl (classe), et classe CStatusBar"
  - "CStatusBarCtrl (classe), et barres d'état MFC"
  - "barres d'état, et classe CStatusBarCtrl"
  - "barres d'état, compatibilité descendante"
  - "barres d'état, implémenter dans MFC"
  - "barres d'état, anciennes avec classe COldStatusBar"
  - "barres d'état, Windows 95 (implémentation)"
  - "indicateurs d'état"
ms.assetid: be5cd876-38e3-4d5c-b8cb-16d57a16a142
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Impl&#233;mentation de la barre d&#39;&#233;tat dans MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un objet de [CStatusBar](../mfc/reference/cstatusbar-class.md) est une barre de contrôle avec une ligne de volets de sortie texte.  Les volets de sortie sont fréquemment utilisés comme des lignes de message et comme indicateurs de états.  Les exemples incluent les lignes de messages d'aide qui expliquent brièvement la commande du menu sélectionnée et les indicateurs qui montrent l'état du ARRÊT DÉFIL, le VERROUILLAGE NUMERIC, ainsi que d'autres index.  
  
 À compter de la version 4,0 de MFC, les barres d'état sont implémentées avec la classe [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md), qui encapsule un contrôle courant de barre d'état.  Pour la compatibilité descendante, MFC conserve l'ancienne implémentation de barres d'état dans la classe **COldStatusBar**.  La documentation pour les versions antérieures de MFC décrit **COldToolBar** sous `CStatusBar`.  
  
 [CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md), une fonction membre nouvelle à MFC 4,0, vous permet de profiter de la prise en charge du contrôle commun Windows de la personnalisation de la barre d'état et de fonctionnalités supplémentaires.  Les fonctions membres de `CStatusBar` vous donne la plupart des fonctionnalités des contrôles communs Windows ; toutefois, lorsque vous appelez `GetStatusBarCtrl`, vous pouvez attribuer aux barres d'état encore plus de caractéristiques d'une barre d'état.  Lorsque vous appelez `GetStatusBarCtrl`, il retourne une référence à un objet de `CStatusBarCtrl`.  Vous pouvez utiliser cette référence pour manipuler le contrôle de la barre d'état.  
  
 L'illustration suivante montre une barre d'état qui affiche plusieurs indicateurs.  
  
 ![Barre d'état](../mfc/media/vc37dy1.png "vc37DY1")  
Une barre d'état  
  
 Comme la barre d'outils, l'objet de la barre d'état est incorporé dans la fenêtre de cadre parente et est créé automatiquement lorsque la fenêtre cadre est construite.  La barre d'état, comme toutes les barres de contrôle, est automatiquement détruite lorsque le cadre parent est détruit.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Mise à jour du texte d'un volet de barre d'état](../mfc/updating-the-text-of-a-status-bar-pane.md)  
  
-   Les classes [CStatusBar](../mfc/reference/cstatusbar-class.md) et [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)de MFC  
  
-   [Barres de contrôles](../mfc/control-bars.md)  
  
-   [Barres de boîte de dialogue](../mfc/dialog-bars.md)  
  
-   [Barres d'outils \(implémentation de la barre d'outils de MFC\)](../mfc/mfc-toolbar-implementation.md)  
  
## Voir aussi  
 [Barres d'état](../mfc/status-bars.md)