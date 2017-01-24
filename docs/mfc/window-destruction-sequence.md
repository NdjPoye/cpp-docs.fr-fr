---
title: "S&#233;quence de destruction de fen&#234;tres | Microsoft Docs"
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
  - "objets CWnd, séquence de destruction"
  - "détruire des fenêtres"
  - "destruction, fenêtres"
  - "séquence (C++)"
  - "séquence (C++), destruction de fenêtres"
  - "fenêtres (C++), détruire"
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# S&#233;quence de destruction de fen&#234;tres
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans l'infrastructure MFC, lorsque l'utilisateur ferme le cadre de la fenêtre, le gestionnaire par défaut d' [OnClose](../Topic/CWnd::OnClose.md) de la fenêtre appelle [DestroyWindow](../Topic/CWnd::DestroyWindow.md).  La dernière fonction membre appelée lorsque la fenêtre Windows est détruite est [OnNcDestroy](../Topic/CWnd::OnNcDestroy.md), qui effectue un peu de nettoyage, appelle la fonction membre d' [Par défaut](../Topic/CWnd::Default.md) pour effectuer le nettoyage Windows, et enfin appelle la fonction membre [PostNcDestroy](../Topic/CWnd::PostNcDestroy.md)virtuelle.  L'implémentation d' [CFrameWnd](../mfc/reference/cframewnd-class.md) d' `PostNcDestroy` supprime l'objet de fenêtre C\+\+.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Allocation et libération de la mémoire de la fenêtre](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Détachement d'un objet CWnd de son HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## Voir aussi  
 [Destruction d'objets fenêtres](../mfc/destroying-window-objects.md)