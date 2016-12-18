---
title: "Fonctions de gestion de la m&#233;moire | Microsoft Docs"
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
  - "fonctions de gestion de la mémoire (runtime d'accès concurrentiel)"
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
caps.latest.revision: 6
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fonctions de gestion de la m&#233;moire
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document décrit les fonctions de gestion de la mémoire que le runtime d'accès concurrentiel fournit pour vous aider à allouer et libérer de la mémoire de façon simultanée.  
  
> [!TIP]
>  Le runtime d'accès concurrentiel fournit un planificateur par défaut. Par conséquent, vous n'êtes pas tenu d'en créer un dans votre application.  Étant donné que le planificateur de tâches vous aide à affiner les performances de vos applications, nous vous recommandons de commencer avec la [Bibliothèque de modèles parallèles](../../parallel/concrt/parallel-patterns-library-ppl.md) ou la [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md) si vous ne connaissez pas encore le runtime d'accès concurrentiel.  
  
 Le runtime d'accès concurrentiel fournit deux fonctions de gestion de la mémoire optimisées pour l'allocation et la libération des blocs de mémoire de façon simultanée.  La fonction [concurrency::Alloc](../Topic/Alloc%20Function.md) alloue un bloc de mémoire avec la taille spécifiée.  La fonction [concurrency::Free](../Topic/Free%20Function.md) libère la mémoire allouée par `Alloc`.  
  
> [!NOTE]
>  Les fonctions `Alloc` et `Free` dépendent l'une de l'autre.  Utilisez la fonction `Free` uniquement pour libérer la mémoire que vous allouez à l'aide de la fonction `Alloc`.  En outre, lorsque vous utilisez la fonction `Alloc` pour allouer de la mémoire, utilisez uniquement la fonction `Free` pour libérer cette mémoire.  
  
 Utilisez les fonctions `Alloc` et `Free` lorsque vous allouez et libérez un jeu fixe de tailles d'allocation de threads ou tâches différents.  Le runtime d'accès concurrentiel met en cache la mémoire qu'il alloue à partir du tas runtime C.  Le runtime d'accès concurrentiel maintient un cache mémoire séparé pour chaque thread en cours d'exécution ; par conséquent, le runtime gère la mémoire sans utiliser de verrous ou de barrières de mémoire.  Une application tire davantage de bénéfices des fonctions `Alloc` et `Free` lorsque les accès au cache mémoire sont plus fréquents.  Par exemple, un thread qui appelle fréquemment`Alloc` et `Free` tire davantage de bénéfices qu'un thread qui appelle principalement `Alloc` ou `Free`.  
  
> [!NOTE]
>  Lorsque vous utilisez ces fonctions de gestion de la mémoire et que votre application utilise beaucoup de mémoire, l'application peut basculer dans une condition de mémoire faible plus tôt que vous ne vous y attendez.  Étant donné que les blocs de mémoire mis en cache par un thread ne sont accessibles à aucun autre thread, si un thread détient beaucoup de mémoire, cette mémoire n'est pas disponible.  
  
## Exemple  
 Pour obtenir un exemple qui utilise les fonctions `Alloc` et `Free` pour améliorer les performances de la mémoire, consultez [Comment : utiliser Alloc et Free pour améliorer les performances de la mémoire](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).  
  
## Voir aussi  
 [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Comment : utiliser Alloc et Free pour améliorer les performances de la mémoire](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)