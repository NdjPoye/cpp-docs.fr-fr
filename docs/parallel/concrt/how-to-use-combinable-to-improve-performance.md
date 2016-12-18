---
title: "Comment&#160;: utiliser la classe combinable pour am&#233;liorer les performances | Microsoft Docs"
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
  - "combinable, classe, exemple"
  - "améliorer les performances parallèles avec combinable [Runtime d’accès concurrentiel]"
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
caps.latest.revision: 17
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: utiliser la classe combinable pour am&#233;liorer les performances
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet exemple montre comment utiliser la classe [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) pour calculer la somme des nombres premiers dans un objet [std::array](../../standard-library/array-class-stl.md).  La classe `combinable` améliore les performances en éliminant l'état partagé.  
  
> [!TIP]
>  Dans certains cas, le mappage parallèle \([concurrency::parallel\_transform](../Topic/parallel_transform%20Function.md)\) et la réduction \([concurrency:: parallel\_reduce](../Topic/parallel_reduce%20Function.md)\) peut améliorer les performances sur `combinable`.  Pour obtenir un exemple qui utilise le mappage et les opérations de réduction pour obtenir les mêmes résultats que cet exemple, consultez [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  
  
## Exemple  
 L'exemple suivant utilise la fonction [std::accumulate](../Topic/accumulate.md) pour calculer la somme des éléments premiers dans un tableau.  Dans cet exemple, `a` est un objet `array` et la fonction `is_prime` détermine si sa valeur d'entrée est première.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_1.cpp)]  
  
## Exemple  
 L'exemple suivant illustre une méthode naïve pour paralléliser l'exemple précédent.  Cet exemple utilise l'algorithme [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) pour traiter le tableau en parallèle et un objet [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) pour synchroniser l'accès à la variable `prime_sum`.  Cet exemple ne monte pas en charge car chaque thread doit attendre que la ressource partagée soit disponible.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_2.cpp)]  
  
## Exemple  
 L'exemple suivant utilise un objet `combinable` pour améliorer les performances de l'exemple précédent.  Cet exemple élimine le besoin en objets de synchronisation ; il monte en charge car l'objet `combinable` permet à chaque thread d'effectuer sa tâche indépendamment.  
  
 Un objet `combinable` s'utilise en général en deux étapes.  En premier lieu, produisez une série de calculs affinés en effectuant un travail en parallèle.  Ensuite, combinez \(ou réduisez\) les calculs en un résultat final.  Cet exemple utilise la méthode [concurrency::combinable::local](../Topic/combinable::local%20Method.md) pour obtenir une référence à la somme locale.  Il utilise ensuite la méthode [concurrency::combinable::combine](../Topic/combinable::combine%20Method.md) et un objet [std::plus](../../standard-library/plus-struct.md) fusionner les calculs locaux dans le résultat final.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_3.cpp)]  
  
## Exemple  
 L'exemple complet suivant calcule la somme des nombres premiers à la fois de façon séquentielle et en parallèle.  L'exemple imprime sur la console le temps requis pour effectuer les deux calculs.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_4.cpp)]  
  
 L'exemple de sortie suivant concerne un ordinateur avec quatre processeurs.  
  
  **1709600813**  
**temps en série : 6178 ms**  
**1709600813**  
**temps en parallèle : 1638 ms**   
## Compilation du code  
 Pour compiler le code, copiez\-le puis collez\-le dans un projet Visual Studio , ou collez\-le dans un fichier nommé parallel\-sum\-of\-primes.cpp puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc parallel\-sum\-of\-primes.cpp**  
  
## Programmation fiable  
 Pour obtenir un exemple qui utilise le mappage et les opérations de réduction pour obtenir les mêmes résultats, consultez [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  
  
## Voir aussi  
 [Conteneurs et objets parallèles](../../parallel/concrt/parallel-containers-and-objects.md)   
 [combinable, classe](../../parallel/concrt/reference/combinable-class.md)   
 [critical\_section, classe](../../parallel/concrt/reference/critical-section-class.md)