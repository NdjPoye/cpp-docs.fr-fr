---
title: 'Comment : utiliser parallel_invoke pour écrire une Routine de tri parallèle | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- task_handle class, example
- task_group class, example
- make_task function, example
- structured_task_group class, example
- improving parallel performance with task groups [Concurrency Runtime]
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53b9699c7ee5d2bd4775f2d6b97dc4d1c5155ce0
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-parallelinvoke-to-write-a-parallel-sort-routine"></a>Comment : utiliser parallel_invoke pour écrire une routine de tri parallèle
Ce document décrit comment utiliser le [parallel_invoke](../../parallel/concrt/parallel-algorithms.md#parallel_invoke) algorithme pour améliorer les performances de l’algorithme de tri bitonique. L’algorithme de tri bitonique manière récursive divise la séquence d’entrée en plus petites partitions triées. L’algorithme de tri bitonique peut s’exécuter en parallèle car chaque opération de partition est indépendante de toutes les autres opérations.  
  
 Bien que le tri bitonique est un exemple d’un *réseau de tri* qui trie toutes les combinaisons des séquences d’entrée, cet exemple trie des séquences dont les longueurs sont une puissance de deux.  
  
> [!NOTE]
>  Cet exemple utilise une routine de tri parallèle à titre d’illustration. Vous pouvez également utiliser les algorithmes de tri intégrées qui la bibliothèque PPL : [concurrency::parallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [concurrency::parallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort), et [concurrency::parallel_ radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Pour plus d’informations, consultez [des algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  
  
##  <a name="top"></a> Sections  
 Ce document décrit les tâches suivantes :  
  
- [Exécution de tri bitonique en série](#serial)  
  
- [À l’aide de parallel_invoke pour exécuter un tri bitonique en parallèle](#parallel)  
  
##  <a name="serial"></a> Exécution de tri bitonique en série  
 L’exemple suivant montre la version sérialisée de l’algorithme de tri bitonique. Le `bitonic_sort` fonction divise la séquence en deux partitions, trie ces partitions dans des directions opposées, puis fusionne les résultats. Cette fonction appelle de manière récursive les deux fois pour trier chaque partition.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]  
  
 [[Haut](#top)]  
  
##  <a name="parallel"></a> À l’aide de parallel_invoke pour exécuter un tri bitonique en parallèle  
 Cette section décrit comment utiliser le `parallel_invoke` algorithme pour l’algorithme de tri bitonique en parallèle.  
  
### <a name="procedures"></a>Procédures  
  
##### <a name="to-perform-the-bitonic-sort-algorithm-in-parallel"></a>Pour exécuter l’algorithme de tri bitonique en parallèle  
  
1.  Ajouter un `#include` directive pour le fichier d’en-tête ppl.h.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]  
  
2.  Ajouter un `using` directive pour le `concurrency` espace de noms.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]  
  
3.  Créer une nouvelle fonction, appelée `parallel_bitonic_mege`, qui utilise le `parallel_invoke` algorithme pour fusionner les séquences en parallèle s’il existe une quantité suffisante de travail à effectuer. Sinon, appelez `bitonic_merge` pour fusionner les séquences en série.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]  
  
4.  Exécutez un processus qui ressemble à celui de l’étape précédente, mais pour le `bitonic_sort` (fonction).  
  
 [!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]  
  
5.  Créer une version surchargée de la `parallel_bitonic_sort` fonction qui trie le tableau dans l’ordre croissant.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]  
  
 Le `parallel_invoke` algorithme réduit la charge en exécutant la dernière série de tâches sur le contexte d’appel. Par exemple, dans le `parallel_bitonic_sort` (fonction), la première tâche s’exécute sur un contexte distinct et la seconde tâche s’exécute sur le contexte d’appel.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_7.cpp)]  
  
 L’exemple complet suivant exécute à la fois le numéro de série et les versions parallèles de l’algorithme de tri bitonique. L’exemple imprime également dans la console le temps nécessaire pour effectuer chaque calcul.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#8](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_8.cpp)]  
  
 L'exemple de sortie suivant concerne un ordinateur équipé de quatre processeurs.  
  
```Output  
serial time: 4353  
parallel time: 1248  
```  
  
 [[Haut](#top)]  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Pour compiler le code, copiez-le et collez-le dans un projet Visual Studio ou collez-le dans un fichier nommé `parallel-bitonic-sort.cpp` , puis exécutez la commande suivante dans une fenêtre d’invite de commandes Visual Studio.  
  
 **CL.exe parallèle bitonique /EHsc-sort.cpp**  
  
## <a name="robust-programming"></a>Programmation fiable  
 Cet exemple utilise le `parallel_invoke` algorithme au lieu du [concurrency::task_group](reference/task-group-class.md) , car la durée de vie de chaque groupe de tâches ne s’étend pas au-delà d’une fonction de classe. Nous vous recommandons d’utiliser `parallel_invoke` lorsque vous pouvez, car il comporte moins d’exécution surcharge que `task group` objets et par conséquent vous permet d’écrire du code plus performant.  
  
 Les versions parallèles de certains algorithmes plus performantes uniquement s’il existe suffisamment travail à effectuer. Par exemple, le `parallel_bitonic_merge` fonction appelle la version sérialisée, `bitonic_merge`, s’il existe moins de 500 éléments dans la séquence. Vous pouvez également planifier votre stratégie globale de tri en fonction de la quantité de travail. Par exemple, il peut être plus efficace d’utiliser la version sérialisée de l’algorithme de tri rapide si le tableau contient moins de 500 éléments, comme indiqué dans l’exemple suivant :  
  
 [!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]  
  
 Comme avec n’importe quel algorithme parallèle, nous recommandons que vous profilez et adapter votre code comme il convient.  
  
## <a name="see-also"></a>Voir aussi  
 [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [parallel_invoke, fonction](reference/concurrency-namespace-functions.md#parallel_invoke)

