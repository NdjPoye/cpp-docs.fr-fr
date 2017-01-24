---
title: "Comment&#160;: &#233;crire une boucle parallel_for_each | Microsoft Docs"
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
  - "écrire une boucle parallel_for_each [Runtime d’accès concurrentiel]"
  - "parallel_for_each, fonction, exemple"
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
caps.latest.revision: 15
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: &#233;crire une boucle parallel_for_each
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet exemple montre comment utiliser l'algorithme [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) pour calculer la quantité de nombres premiers dans un objet [std::array](../../standard-library/array-class-stl.md) en parallèle.  
  
## Exemple  
 L'exemple suivant calcule la quantité de nombres premiers dans un tableau à deux reprises.  L'exemple utilise d'abord l'algorithme [std::for\_each](../Topic/for_each.md) pour calculer le numéro séquentiel.  L'exemple utilise ensuite l'algorithme `parallel_for_each` pour effectuer la même tâche en parallèle.  L'exemple imprime également dans la console le temps requis pour effectuer les deux calculs.  
  
 [!code-cpp[concrt-parallel-count-primes#1](../../parallel/concrt/codesnippet/CPP/how-to-write-a-parallel-for-each-loop_1.cpp)]  
  
 L'exemple de sortie suivant concerne un ordinateur avec quatre processeurs.  
  
  **version sérialisée :**  
**trouvé 17984 premiers nombres**  
**a nécessité 6115 ms**  
**version parallèle :**  
**trouvé 17984 premiers nombres**  
**a nécessité 1653 ms**   
## Compilation du code  
 Pour compiler le code, copiez\-le puis collez\-le dans un projet Visual Studio , ou collez\-le dans un fichier nommé parallel\-count\-primes.cpp puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc parallel\-count\-primes.cpp**  
  
## Programmation fiable  
 L'expression lambda que l'exemple passe à l'algorithme `parallel_for_each` utilise la fonction `InterlockedIncrement` pour permettre aux itérations parallèles de la boucle d'incrémenter le compteur simultanément.  Si vous utilisez des fonctions telles qu'`InterlockedIncrement` pour synchroniser l'accès aux ressources partagées, vous pouvez introduire des goulots d'étranglement au niveau des performances dans votre code.  Vous pouvez utiliser un mécanisme de synchronisation sans verrou, par exemple la classe [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md), pour éliminer l'accès simultané aux ressources partagées.  Pour obtenir un exemple qui utilise la classe `combinable` de cette manière, consultez [Comment : utiliser la classe combinable pour améliorer les performances](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md).  
  
## Voir aussi  
 [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)   
 [parallel\_for\_each, fonction](../Topic/parallel_for_each%20Function.md)