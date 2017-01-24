---
title: "Comment &#233;viter les sources d&#39;incident dans les programmes multithread | Microsoft Docs"
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
  - "erreurs (C++), programmes multithread"
  - "multithreading (C++), dépanner"
  - "threads (C++), dépanner"
  - "dépanner (C++), multithreading"
ms.assetid: 06cc231d-bb5a-409d-8bd3-676c9e2a8c5b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment &#233;viter les sources d&#39;incident dans les programmes multithread
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

De multiples incidents apparaissent lors de la création, de la liaison ou de l'exécution d'un programme multithread en langage C.  Quelques\-uns des problèmes les plus communs sont décrits dans le tableau suivant. \(Pour une description similaire sous l'angle MFC, consultez [Multithreading : conseils de programmation](../../parallel/multithreading-programming-tips.md).\)  
  
|Problème|Cause probable|  
|--------------|--------------------|  
|Vous obtenez une boîte de message indiquant que votre programme a provoqué une violation de protection.|De nombreuses erreurs de programmation Win32 provoquent des violations de protection.  L'assignation indirecte de données à des pointeurs nuls est une cause fréquente de violations de protection.  Dans ce contexte, votre programme essaie d'accéder à la mémoire qui ne lui appartient pas, d'où la violation de protection.<br /><br /> Il est relativement facile de détecter la cause d'une violation de protection. Il suffit de compiler le programme à l'aide d'informations de débogage, puis de l'exécuter avec le débogueur dans l'environnement Visual C\+\+.  Quand l'erreur de protection se produit, Windows passe la main au débogueur, et le curseur est positionné sur la ligne à l'origine de l'incident.|  
|Votre programme génère de nombreuses erreurs de compilation et de liaison.|Vous pouvez éliminer de nombreuses sources d'incident potentielles en attribuant au niveau d'avertissement du compilateur l'une de ses valeurs les plus élevées et en faisant attention aux messages d'avertissement.  Grâce aux options de niveau d'avertissement 3 ou 4, vous pouvez détecter les conversions de données involontaires, les prototypes de fonctions manquants et l'utilisation de fonctions non\-ANSI.|  
  
## Voir aussi  
 [Multithreading à l'aide de C et de Win32](../../parallel/multithreading-with-c-and-win32.md)