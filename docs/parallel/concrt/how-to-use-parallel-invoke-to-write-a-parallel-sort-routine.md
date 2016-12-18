---
title: "Comment&#160;: utiliser parallel_invoke pour &#233;crire une routine de tri parall&#232;le | Microsoft Docs"
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
  - "task_handle, exemple de classe"
  - "task_group, exemple de classe"
  - "make_task, exemple de fonction"
  - "structured_task_group, exemple de classe"
  - "améliorer les performances parallèles avec des groupes de tâches (runtime d'accès concurrentiel)"
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
caps.latest.revision: 23
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: utiliser parallel_invoke pour &#233;crire une routine de tri parall&#232;le
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document décrit comment utiliser l'algorithme [parallel\_invoke](../Topic/parallel_invoke%20Function.md) pour améliorer les performances de l'algorithme de tri bitonique.  L'algorithme de tri bitonique divise de manière récursive la séquence d'entrée en plus petites partitions triées.  L'algorithme de tri bitonique peut s'exécuter en parallèle car chaque opération de partition est indépendante de toutes les autres opérations.  
  
 Bien que le tri bitonique soit un exemple de *réseau de tri* qui trie toutes les combinaisons de séquences d'entrée, cet exemple trie des séquences dont les longueurs sont une puissance de deux.  
  
> [!NOTE]
>  Cet exemple utilise une routine de tri parallèle pour l'illustration.  Vous pouvez également utiliser les algorithmes de tri intégrés que le PPL fournit : [concurrency::parallel\_sort](../Topic/parallel_sort%20Function.md), [concurrency::parallel\_buffered\_sort](../Topic/parallel_buffered_sort%20Function.md), et [concurrency::parallel\_radixsort](../Topic/parallel_radixsort%20Function.md).  Pour plus d'informations, consultez [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  
  
##  <a name="top"></a> Sections  
 Ce document décrit les tâches suivantes :  
  
-   [Exécution de tri bitonique de façon séquentielle](#serial)  
  
-   [Utilisation de parallel\_invoke pour exécuter un tri bitonique en parallèle](#parallel)  
  
##  <a name="serial"></a> Exécution de tri bitonique de façon séquentielle  
 L'exemple suivant illustre la version sérialisée de l'algorithme de tri bitonique.  La fonction `bitonic_sort` divise la séquence en deux partitions, trie ces partitions dans des directions opposées, puis fusionne les résultats.  Cette fonction s'appelle de manière récursive à deux reprises pour trier chaque partition.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]  
  
 \[[Premières](#top)\]  
  
##  <a name="parallel"></a> Utilisation de parallel\_invoke pour exécuter un tri bitonique en parallèle  
 Cette section décrit comment utiliser l'algorithme `parallel_invoke` pour exécuter l'algorithme de tri bitonique en parallèle.  
  
### Procédures  
  
##### Pour exécuter l'algorithme de tri bitonique en parallèle  
  
1.  Ajoutez une directive `#include` pour le fichier d'en\-tête ppl.h.  
  
     [!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]  
  
2.  Ajoutez une directive `using` pour l'espace de noms `concurrency`.  
  
     [!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]  
  
3.  Créez une fonction, appelée `parallel_bitonic_mege`, qui utilise l'algorithme `parallel_invoke` pour fusionner les séquences en parallèle si la quantité de travail à effectuer est suffisante.  Sinon, appelez `bitonic_merge` pour fusionner les séquences de façon séquentielle.  
  
     [!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]  
  
4.  Exécutez un processus qui ressemble à celui de l'étape précédente, mais pour la fonction `bitonic_sort`.  
  
     [!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]  
  
5.  Créez une version surchargée de la fonction `parallel_bitonic_sort`, qui trie le tableau en ordre croissant.  
  
     [!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]  
  
 L'algorithme `parallel_invoke` réduit la charge en exécutant la dernière des séries de tâches sur le contexte appelant.  Par exemple, dans la fonction `parallel_bitonic_sort`, la première tâche s'exécute sur un contexte distinct et la seconde tâche s'exécute sur le contexte appelant.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#5](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_7.cpp)]  
  
 L'exemple complet suivant exécute à la fois les versions séquentielles et parallèles de l'algorithme de tri bitonique.  L'exemple imprime également sur la console le temps requis pour effectuer chaque calcul.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#8](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_8.cpp)]  
  
 L'exemple de sortie suivant concerne un ordinateur avec quatre processeurs.  
  
  **temps série : 4353**  
**temps parallèle : 1248** \[[Premières](#top)\]  
  
## Compilation du code  
 Pour compiler le code, copiez\-le puis collez\-le dans un projet `Visual Studio`, ou collez\-le dans un fichier nommé parallel\-bitonic\-sort.cpp puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc parallel\-bitonic\-sort.cpp**  
  
## Programmation fiable  
 Cet exemple utilise l'algorithme `parallel_invoke` au lieu de la classe [concurrency::task\_group](../Topic/task_group%20Class.md), car la durée de vie de chaque groupe de tâches ne s'étend pas au\-delà d'une fonction.  Dans la mesure du possible, nous vous conseillons d'utiliser `parallel_invoke`, car il a une charge d'exécution inférieure aux objets `task group`. Par conséquent, il permet d'écrire du code plus performant.  
  
 Les versions parallèles de certains algorithmes offrent de meilleures performances uniquement lorsqu'il y a une quantité de travail suffisante à effectuer.  Par exemple, la fonction `parallel_bitonic_merge` appelle la version sérialisée, `bitonic_merge`, s'il y a 500 éléments ou moins dans la séquence.  Vous pouvez également organiser votre stratégie de tri globale en fonction de la quantité de travail.  Par exemple, il peut s'avérer plus efficace d'utiliser la version sérialisée de l'algorithme de tri rapide si le tableau comporte moins de 500 éléments, comme indiqué dans l'exemple suivant :  
  
 [!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]  
  
 À l'instar de n'importe quel algorithme parallèle, nous vous conseillons de profiler et d'adapter votre code en fonction de vos besoins.  
  
## Voir aussi  
 [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [parallel\_invoke, fonction](../Topic/parallel_invoke%20Function.md)