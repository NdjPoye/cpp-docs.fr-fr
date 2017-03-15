---
title: "Comment&#160;: utiliser la classe combinable pour combiner des ensembles | Microsoft Docs"
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
  - "combinable, exemple de classe"
  - "combiner des ensembles avec combinable (runtime d'accès concurrentiel)"
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
caps.latest.revision: 14
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: utiliser la classe combinable pour combiner des ensembles
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique indique comment utiliser la classe [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) pour calculer le jeu de nombres premiers.  
  
## Exemple  
 L'exemple suivant calcule le jeu de nombres premiers à deux reprises.  Chaque calcul stocke le résultat dans un objet [std::bitset](../../standard-library/bitset-class.md).  L'exemple calcule d'abord le jeu de façon séquentielle, puis en parallèle.  L'exemple imprime également dans la console le temps requis pour effectuer les deux calculs.  
  
 Cet exemple utilise l'algorithme [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) et un objet `combinable` pour générer des groupes de threads locaux.  Il utilise ensuite la méthode [concurrency::combinable::combine\_each](../Topic/combinable::combine_each%20Method.md) pour combiner les groupes de threads locaux dans le jeu final.  
  
 [!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-combine-sets_1.cpp)]  
  
 L'exemple de sortie suivant concerne un ordinateur avec quatre processeurs.  
  
  **temps en série : 312 ms**  
**temps en parallèle : 78 ms**   
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio, ou collez\-le dans un fichier nommé `parallel-combine-primes.cpp` puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc parallel\-combine\-primes.cpp**  
  
## Voir aussi  
 [Conteneurs et objets parallèles](../../parallel/concrt/parallel-containers-and-objects.md)   
 [combinable, classe](../../parallel/concrt/reference/combinable-class.md)   
 [combinable::combine\_each, méthode](../Topic/combinable::combine_each%20Method.md)