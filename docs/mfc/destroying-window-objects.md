---
title: "Destruction d&#39;objets fen&#234;tres | Microsoft Docs"
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
  - "fenêtres frame, détruire"
  - "objets fenêtres, supprimer"
  - "objets fenêtres, détruire"
  - "objets fenêtres, supprimer"
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Destruction d&#39;objets fen&#234;tres
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prenez soin avec vos propres fenêtres enfants de détruire l'objet fenêtre C\+\+ lorsque l'utilisateur a fini avec la fenêtre.  Si ces objets ne sont pas détruits, votre application ne récupère pas la mémoire.  Heureusement, l'infrastructure gère la destruction ainsi que la création des fenêtres cadres, vues, et boîtes de dialogue.  Si vous créez des fenêtres supplémentaires, vous devez vous charger de les détruire.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Séquence de destruction de fenêtres](../mfc/window-destruction-sequence.md)  
  
-   [Allocation et libération de la mémoire de la fenêtre](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Détachement d'un objet CWnd de son HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [Séquence générale de création d'une fenêtre](../mfc/general-window-creation-sequence.md)  
  
-   [Destruction des fenêtres cadres](../mfc/destroying-frame-windows.md)  
  
## Voir aussi  
 [Objets fenêtres](../mfc/window-objects.md)