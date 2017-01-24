---
title: "Introduction to ATL Window Classes | Microsoft Docs"
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
  - "window classes"
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Introduction to ATL Window Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes ATL suivantes sont conçues pour implémenter et manipuler des fenêtres :  
  
-   [CWindow](../atl/reference/cwindow-class.md) vous permet de joindre un handle de fenêtre à l'objet d' `CWindow` .  Appelez ensuite des méthodes d' `CWindow` pour manipuler la fenêtre.  
  
-   [CWindowImpl](../atl/reference/cwindowimpl-class.md) vous permet d'implémenter une nouvelle fenêtre et des messages de processus avec une table des messages.  Vous pouvez créer une fenêtre en fonction de nouvelles fenêtres surclassement classe, une classe existante, ou sous\-classe une fenêtre existante.  
  
-   [CDialogImpl](../atl/reference/cdialogimpl-class.md) vous permet d'implémenter des messages modaux ou d'une boîte de dialogue non modale et de processus avec une table des messages.  
  
-   [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) est une classe prégénérées qui implémente une fenêtre dont la table des messages est contenue dans une autre classe.  Utilisation `CContainedWindowT` vous permet de centraliser le traitement des messages dans une classe.  
  
-   [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) vous permet d'implémenter une boîte de dialogue \(modale ou non modale\) que des contrôles ActiveX d'hôtes.  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) vous permet d'implémenter une boîte de dialogue modale avec la fonctionnalité de base.  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) vous permet d'implémenter une fenêtre qui héberge un contrôle ActiveX.  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md) vous permet d'implémenter une fenêtre qui héberge un contrôle ActiveX autorisé.  
  
 Outre les classes de fenêtres spécifiques, ATL fournit plusieurs classes conçues pour faciliter l'implémentation d'un objet window ATL.  Elles se présentent comme suit :  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) gère les informations d'une nouvelle classe de fenêtre.  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) et [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) fournissent une méthode simple de standardiser les caractéristiques d'un objet window ATL.  
  
## Voir aussi  
 [classes de fenêtre](../atl/atl-window-classes.md)