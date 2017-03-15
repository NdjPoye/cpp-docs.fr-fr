---
title: "Comment&#160;: utiliser des conteneurs parall&#232;les pour une efficacit&#233; accrue | Microsoft Docs"
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
  - "augmenter l’efficacité avec des conteneurs parallèles [Runtime d’accès concurrentiel]"
  - "concurrent_queue, classe, exemples"
  - "concurrent_vector, classe, exemples"
ms.assetid: bd00046d-e9b6-4ae1-b661-3995f671b867
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Comment&#160;: utiliser des conteneurs parall&#232;les pour une efficacit&#233; accrue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique indique comment utiliser des conteneurs parallèles pour stocker et accéder efficacement à des données en parallèle.  
  
 L'exemple de code calcule l'ensemble des nombres premiers et des nombres de Carmichael en parallèle.  Ensuite, pour chaque nombre de Carmichael, le code calcule les facteurs premiers de ce nombre.  
  
## Exemple  
 L'exemple suivant illustre la fonction `is_prime`, qui détermine si une valeur d'entrée est un nombre premier, et la fonction `is_carmichael`, qui détermine si la valeur d'entrée est un nombre de Carmichael.  
  
 [!code-cpp[concrt-carmichael-primes#1](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-containers-to-increase-efficiency_1.cpp)]  
  
## Exemple  
 L'exemple suivant utilise les fonctions `is_carmichael` et `is_prime` pour calculer les ensembles de nombres premiers et de nombres de Carmichael.  L'exemple utilise les algorithmes [concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md) et [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) pour calculer chaque ensemble en parallèle.  Pour plus d'informations sur les algorithmes parallèles, consultez [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  
  
 Cet exemple utilise un objet [concurrency::concurrent\_queue](../../parallel/concrt/reference/concurrent-queue-class.md) pour stocker l'ensemble des nombres de Carmichael, car il utilisera ultérieurement cet objet comme file d'attente de travail.  Il utilise un objet [concurrency::concurrent\_vector](../../parallel/concrt/reference/concurrent-vector-class.md) pour stocker l'ensemble de nombres premiers, car il itérera ultérieurement au sein de cet ensemble pour rechercher les facteurs premiers.  
  
 [!code-cpp[concrt-carmichael-primes#2](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-containers-to-increase-efficiency_2.cpp)]  
  
## Exemple  
 L'exemple suivant illustre la fonction `prime_factors_of`, qui utilise la division par évaluation pour rechercher tous les facteurs premiers de la valeur donnée.  
  
 Cette fonction utilise l'algorithme [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) pour itérer au sein de la collection de nombres premiers.  L'objet `concurrent_vector` permet à la boucle parallèle d'ajouter simultanément des facteurs premiers au résultat.  
  
 [!code-cpp[concrt-carmichael-primes#3](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-containers-to-increase-efficiency_3.cpp)]  
  
## Exemple  
 Cet exemple traite chaque élément dans la file d'attente de nombres de Carmichael en appelant la fonction `prime_factors_of` pour calculer ses facteurs premiers.  Il utilise un groupe de tâches pour effectuer ce travail en parallèle.  Pour plus d'informations sur les groupes de tâches, consultez [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Cet exemple imprime les facteurs premiers pour chaque nombre de Carmichael si ce nombre possède plus de quatre facteurs premiers.  
  
 [!code-cpp[concrt-carmichael-primes#4](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-containers-to-increase-efficiency_4.cpp)]  
  
## Exemple  
 Le code suivant montre l'exemple complet, qui utilise des conteneurs parallèles pour calculer les facteurs premiers des nombres de Carmichael.  
  
 [!code-cpp[concrt-carmichael-primes#5](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-containers-to-increase-efficiency_5.cpp)]  
  
 Cet exemple génère l'exemple de sortie suivant.  
  
  **Les facteurs principaux à 9890881 sont : 7 11 13 41.241.**  
**Les facteurs principaux à 825265 sont : 5 7 17 19 73.**  
**Les facteurs principaux à 1050985 sont : 5 13 19 23 37.**   
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio , ou collez\-le dans un fichier nommé `carmichael-primes.cpp` puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc carmichael\-primes.cpp**  
  
## Voir aussi  
 [Conteneurs et objets parallèles](../../parallel/concrt/parallel-containers-and-objects.md)   
 [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Classe concurrent\_vector](../../parallel/concrt/reference/concurrent-vector-class.md)   
 [concurrent\_queue, classe](../../parallel/concrt/reference/concurrent-queue-class.md)   
 [parallel\_invoke, fonction](../Topic/parallel_invoke%20Function.md)   
 [parallel\_for, fonction](../Topic/parallel_for%20Function.md)   
 [task\_group, classe](../Topic/task_group%20Class.md)