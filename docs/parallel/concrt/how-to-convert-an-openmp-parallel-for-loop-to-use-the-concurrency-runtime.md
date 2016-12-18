---
title: "Comment&#160;: convertir une boucle OpenMP parall&#232;le pour utiliser le runtime d’acc&#232;s concurrentiel | Microsoft Docs"
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
  - "convertir d’OpenMP en runtime d’accès concurrentiel, for (boucles parallèles)"
  - "convertir d’OpenMP en runtime d’accès concurrentiel, boucles parallèles"
  - "for (boucles parallèles), convertir d’OpenMP en runtime d’accès concurrentiel"
  - "boucles parallèles, convertir d’OpenMP en runtime d’accès concurrentiel"
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
caps.latest.revision: 13
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: convertir une boucle OpenMP parall&#232;le pour utiliser le runtime d’acc&#232;s concurrentiel
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet exemple explique comment convertir une boucle de base qui utilise les directives [parallel](../../parallel/openmp/reference/parallel.md) et [for](../../parallel/openmp/reference/for-openmp.md) OpenMP pour utiliser l'algorithme de runtime d'accès concurrentiel [concurrency::parallel\_for](../Topic/parallel_for%20Function.md).  
  
## Exemple  
 Cet exemple utilise OpenMP et le runtime d'accès concurrentiel pour calculer le nombre de nombres premiers dans un tableau de valeurs aléatoires.  
  
 [!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/CPP/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]  
  
 Cet exemple génère la sortie suivante.  
  
  **Utilisation de OpenMP…**  
**a trouvé 107254 nombres premiers.**  
**utilisation du runtime d'accès concurrentiel...**  
**trouvé 107254 nombres premiers.** L'algorithme `parallel_for` et OpenMP 3.0 permettent au type d'index d'être de type intégral signé ou de type intégral non signé.  L'algorithme `parallel_for` vérifie également que la plage spécifiée ne dépasse pas un type signé.  Les versions OpenMP 2.0 et 2.5 n'autorisent que les types d'index intégraux signés.  OpenMP ne valide pas la plage d'index.  
  
 La version de cet exemple qui utilise le runtime d'accès concurrentiel utilise également un objet [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) au lieu de la directive [atomic](../../parallel/openmp/reference/atomic.md) pour incrémenter la valeur de compteur sans nécessiter de synchronisation.  
  
 Pour plus d'informations sur `parallel_for` et d'autres algorithmes parallèles, consultez [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  Pour plus d'informations sur la classe `combinable`, consultez [Conteneurs et objets parallèles](../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Exemple  
 Cet exemple modifie l'exemple précédent pour agir sur un objet [std::array](../../standard-library/array-class-stl.md) plutôt que sur un tableau natif.  Étant donné que les versions OpenMP 2.0 et 2.5 n'autorisent que les types d'index intégraux signés dans un élément `parallel` `for`, vous ne pouvez pas utiliser d'itérateurs pour accéder aux éléments d'un conteneur de la bibliothèque de modèles Standard \(STL\) en parallèle.  La bibliothèque de modèles parallèles \(PPL\) fournit l'algorithme [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md), qui exécute des tâches, en parallèle, sur un conteneur itératif, tels que ceux fournis par la bibliothèque STL.  Il utilise la même logique de partitionnement que l'algorithme `parallel_for`.  L'algorithme `parallel_for_each` ressemble à l'algorithme [std::for\_each](../Topic/for_each.md) STL, à l'exception près que l'algorithme `parallel_for_each` exécute les tâches simultanément.  
  
 [!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/CPP/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]  
  
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio , ou collez\-le dans un fichier nommé `concrt-omp-count-primes.cpp`. Exécutez ensuite la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-count\-primes.cpp**  
  
## Voir aussi  
 [Migration d'OpenMP au runtime d'accès concurrentiel](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)   
 [Conteneurs et objets parallèles](../../parallel/concrt/parallel-containers-and-objects.md)