---
title: "Allocation et lib&#233;ration de la m&#233;moire Windows | Microsoft Docs"
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
  - "allocation de mémoire, objets fenêtres"
  - "désallocation de mémoire"
  - "désallocation de mémoire, fenêtre (mémoire)"
  - "stockage des objets fenêtres"
  - "stockage des objets fenêtres, allouer"
  - "objets fenêtres, libérer de la mémoire pour"
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Allocation et lib&#233;ration de la m&#233;moire Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

N'utilisez pas l'opérateur C\+\+ **supprimer** pour détruire une fenêtre cadre ou une vue.  Appelez la fonction membre `CWnd` `DestroyWindow` plutôt.  Les fenêtres cadres doivent, par conséquent, être allouées sur le tas avec l'opérateur **new**.  Soyez attentif lors de l'allocation des fenêtres cadres sur le frame de pile ou globalement.  D'autres fenêtres doivent être allouées sur le frame de pile dès que possible.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Création de fenêtres](../mfc/creating-windows.md)  
  
-   [Séquence de destruction de fenêtres](../mfc/window-destruction-sequence.md)  
  
-   [Détachement d'un objet CWnd de son HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## Voir aussi  
 [Destruction d'objets fenêtres](../mfc/destroying-window-objects.md)