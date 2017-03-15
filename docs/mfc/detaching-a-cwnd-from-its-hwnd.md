---
title: "D&#233;tachement d&#39;un objet CWnd de son HWND | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "objets CWnd, détacher de HWND"
  - "Detach (méthode) (classe CWnd)"
  - "détacher des CWnd de HWND"
  - "HWND, détacher CWnd de"
  - "supprimer des HWND de CWnd"
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# D&#233;tachement d&#39;un objet CWnd de son HWND
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous devez éviter la relation `HWND` d'objet, MFC fournit une fonction membre `CWnd`, [Détacher](../Topic/CWnd::Detach.md), qui déconnecte l'objet fenêtre C\+\+ de la fenêtre du windows.  Cela empêché le destructeur de détruire la fenêtre du windows lorsque l'objet est détruit.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Création de fenêtres](../mfc/creating-windows.md)  
  
-   [Séquence de destruction de fenêtres](../mfc/window-destruction-sequence.md)  
  
-   [Allocation et libération de la mémoire de la fenêtre](../mfc/allocating-and-deallocating-window-memory.md)  
  
## Voir aussi  
 [Objets fenêtres](../mfc/window-objects.md)