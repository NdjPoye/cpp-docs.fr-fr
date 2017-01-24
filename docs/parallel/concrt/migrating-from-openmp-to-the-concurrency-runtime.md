---
title: "Migration d&#39;OpenMP au runtime d&#39;acc&#232;s concurrentiel | Microsoft Docs"
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
  - "Concurrency Runtime, effectuer la migration à partir d'OpenMP"
  - "OpenMP, migrer vers le runtime d'accès concurrentiel"
ms.assetid: 9bab7bb1-e45d-44b2-8509-3b226be2c93b
caps.latest.revision: 12
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Migration d&#39;OpenMP au runtime d&#39;acc&#232;s concurrentiel
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le runtime d'accès concurrentiel autorise divers modèles de programmation.  Ces modèles peuvent se chevaucher ou compléter les modèles d'autres bibliothèques.  Les documents de cette section comparent [OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md) au runtime d'accès concurrentiel et fournissent des exemples sur la migration du code OpenMP existant pour utiliser le runtime d'accès concurrentiel.  
  
 Le modèle de programmation OpenMP est défini par une norme ouverte et a des liaisons bien définies aux langages de programmation Fortran et C\/ C\+\+.  Les versions 2.0 et 2.5 d'OpenMP, qui sont prises en charge par le compilateur Visual C\+\+, sont adaptées aux algorithmes parallèles qui sont itératifs, c'est\-à\-dire qui effectuent une itération parallèle sur un tableau de données.  En plus des tâches itératives, OpenMP 3.0 prend en charge les tâches non\-itératives.  
  
 OpenMP est très efficace lorsque le degré de parallélisme est prédéterminé et qu'il correspond aux ressources disponibles sur le système.  Le modèle OpenMP convient particulièrement à l'informatique hautes performances, où les problèmes de calcul à grande échelle sont répartis sur les ressources de traitement de l'ordinateur.  Dans ce scénario, l'environnement matériel est généralement fixe et le développeur peut raisonnablement s'attendre à disposer d'un accès exclusif à toutes les ressources de calcul lors de l'exécution de l'algorithme.  
  
 En revanche, les environnements informatique moins contraints peuvent ne pas constituer une bonne correspondance pour OpenMP.  Par exemple, les problèmes récursifs \(tels que l'algorithme de tri rapide ou la recherche dans une arborescence de données\) sont plus difficiles à implémenter à l'aide des versions 2.0 et 2.5 d'OpenMP.  Le runtime d'accès concurrentiel complète les fonctions d'OpenMP en fournissant la [bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md) et la [bibliothèque de modèles parallèles](../../parallel/concrt/parallel-patterns-library-ppl.md).  La bibliothèque d'agents asynchrones prend en charge le parallélisme des tâches de granularité grossière. La bibliothèque de modèles parallèles prend en charge des tâches parallèles de granularité plus fine.  Le runtime d'accès concurrentiel fournit l'infrastructure requise pour exécuter des opérations en parallèle, afin que vous puissiez vous concentrer sur la logique de votre application.  Toutefois, étant donné que le runtime d'accès concurrentiel autorise divers modèles de programmation, sa charge de planification peut être plus importante que celle d'autres bibliothèques d'accès concurrentiel telles qu'OpenMP.  Par conséquent, nous conseillons de tester les performances de façon incrémentielle lorsque vous convertissez votre code OpenMP existant pour utiliser le runtime d'accès concurrentiel.  
  
## À quel moment migrer d'OpenMP vers le runtime d'accès concurrentiel  
 Il peut être avantageux de migrer un code OpenMP existant pour utiliser le runtime d'accès concurrentiel dans les situations suivantes :  
  
|Situations|Avantages du runtime d'accès concurrentiel|  
|----------------|------------------------------------------------|  
|Vous avez besoin d'une infrastructure de programmation simultanée extensible.|Une grande partie des fonctionnalités du runtime d'accès concurrentiel peuvent être étendues.  Vous pouvez également combiner des fonctionnalités existantes pour en composer de nouvelles.  Étant donné qu'OpenMP repose sur des directives de compilateur, son extension n'est pas simple.|  
|Votre application tirerait parti du blocage coopératif.|Lorsqu'une tâche bloque, car elle a besoin d'une ressource qui n'est pas encore disponible, le runtime d'accès concurrentiel peut effectuer d'autres tâches pendant que la première tâche attend la ressource.|  
|Votre application tirerait parti de l'équilibrage de charge dynamique.|Le runtime d'accès concurrentiel utilise un algorithme de planification qui ajuste l'allocation de ressources de calcul à mesure que les charges de travail évoluent.  Dans OpenMP, lorsque le planificateur alloue des ressources de calcul à une zone parallèle, ces allocations de ressources sont constantes pendant l'ensemble du calcul.|  
|Vous avez besoin de la prise en charge de la gestion des exceptions.|La bibliothèque de modèles parallèles vous permet d'intercepter des exceptions à l'intérieur et à l'extérieur d'une région ou d'une boucle parallèle.  Dans OpenMP, vous devez gérer l'exception à l'intérieur de la région ou de la boucle parallèle.|  
|Vous avez besoin d'un mécanisme d'annulation.|La bibliothèque de modèles parallèles permet aux applications d'annuler les tâches individuelles et les arborescences de travail parallèle.  OpenMP a besoin que l'application implémente son propre mécanisme d'annulation.|  
|Le code parallèle doit se terminer dans un contexte différent de celui dans lequel il démarre.|Le runtime d'accès concurrentiel vous permet de démarrer une tâche dans un contexte, puis d'attendre ou d'annuler cette tâche dans un autre contexte.  Dans OpenMP, tout travail parallèle doit se terminer dans le contexte dans lequel il démarre.|  
|Vous avez besoin de la prise en charge du débogage améliorée.|Visual Studio propose les fenêtres **Pilles parallèles** et **Tâches parallèles**, afin que vous puissiez déboguer plus facilement des applications multithread.<br /><br /> Pour plus d'informations sur la prise en charge du débogage pour le runtime d'accès concurrentiel, consultez [Utilisation de la fenêtre Tâches](../Topic/Using%20the%20Tasks%20Window.md), [Utilisation de la fenêtre Piles parallèles](../Topic/Using%20the%20Parallel%20Stacks%20Window.md) et [Procédure pas à pas : débogage d'une application parallèle](../Topic/Walkthrough:%20Debugging%20a%20Parallel%20Application.md).|  
  
## Dans quelles situations ne pas migrer d'OpenMP vers le runtime d'accès concurrentiel  
 Les cas suivants décrivent les situations dans lesquelles il peut ne pas être approprié de migrer un code OpenMP existant pour utiliser le runtime d'accès concurrentiel.  
  
|Situations|Explication|  
|----------------|-----------------|  
|Votre application répond déjà à vos besoins.|Si vous êtes satisfait des performances de votre application et de la prise en charge du débogage actuelle, la migration peut ne pas être appropriée.|  
|L'activité des corps des boucles parallèles est peu importante.|La charge du planificateur de tâches du runtime d'accès concurrentiel peut ne pas l'emporter sur les avantages qui découlent de l'exécution du corps de la boucle en parallèle, notamment lorsque le corps de la boucle est relativement petit.|  
|Votre application est écrite en C.|Étant donné que le runtime d'accès concurrentiel utilise de nombreuses fonctionnalités C\+\+, il ne convient pas forcément lorsque vous ne pouvez pas écrire du code qui permet à l'application C de l'utiliser complètement.|  
  
## Rubriques connexes  
 [Comment : convertir une boucle OpenMP parallèle pour utiliser le runtime d’accès concurrentiel](../../parallel/concrt/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime.md)  
 À partir d'une boucle de base qui utilise les directives OpenMP [parallel](../../parallel/openmp/reference/parallel.md) et [for](../../parallel/openmp/reference/for-openmp.md), cet exemple montre comment la convertir pour utiliser l'algorithme de runtime d'accès concurrentiel [concurrency::parallel\_for](../Topic/parallel_for%20Function.md).  
  
 [Comment : convertir une boucle OpenMP qui a recours à l’annulation pour utiliser le runtime d’accès concurrentiel](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)  
 À partir d'une boucle [parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md) OpenMP qui ne requiert pas l'exécution de toutes les itérations, cet exemple montre comment la convertir pour utiliser le mécanisme d'annulation du runtime d'accès concurrentiel.  
  
 [Comment : convertir une boucle OpenMP qui a recours à la gestion des exceptions pour utiliser le runtime d'accès concurrentiel](../../parallel/concrt/convert-an-openmp-loop-that uses-exception-handling.md)  
 À partir d'une boucle [parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md) OpenMP qui exécute la gestion des exceptions, cet exemple montre comment la convertir pour utiliser le mécanisme de gestion des exceptions du runtime d'accès concurrentiel.  
  
 [Comment : convertir une boucle OpenMP qui a recours à une variable de réduction pour utiliser le runtime d’accès concurrentiel](../../parallel/concrt/convert-an-openmp-loop-that-uses-a-reduction-variable.md)  
 À partir d'une boucle [parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md) OpenMP qui utilise la clause [reduction](../../parallel/openmp/reference/reduction.md), cet exemple montre comment la convertir pour utiliser le runtime d'accès concurrentiel.  
  
## Voir aussi  
 [Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)   
 [OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Bibliothèque de modèles parallèles](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)