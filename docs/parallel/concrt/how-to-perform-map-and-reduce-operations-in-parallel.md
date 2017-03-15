---
title: "Comment&#160;: ex&#233;cuter des op&#233;rations de mappage et de r&#233;duction en parall&#232;le | Microsoft Docs"
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
  - "parallel_transform (fonction), par exemple"
  - "mappage et réduction en parallèle, exemple"
  - "parallel_reduce (fonction), par exemple"
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Comment&#160;: ex&#233;cuter des op&#233;rations de mappage et de r&#233;duction en parall&#232;le
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet exemple montre comment utiliser le [concurrency::parallel_transform](../Topic/parallel_transform%20Function.md) et [concurrency::parallel_reduce](../Topic/parallel_reduce%20Function.md) algorithmes et [concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) pour compter les occurrences de mots dans les fichiers de classe.  
  
 Un *carte* opération applique une fonction à chaque valeur dans une séquence. Un *Réduire* opération regroupe les éléments d’une séquence dans une seule valeur. Vous pouvez utiliser la bibliothèque STL (Standard Template Library) [std::transform](../Topic/transform.md)[std::accumulate](../Topic/accumulate.md) classes map et réduire les opérations. Toutefois, pour améliorer les performances en réponse à de nombreux problèmes, vous pouvez utiliser l'algorithme `parallel_transform` pour effectuer l'opération de mappage en parallèle et l'algorithme `parallel_reduce` pour effectuer l'opération de réduction en parallèle. Dans certains cas, vous pouvez utiliser `concurrent_unordered_map` pour effectuer le mappage et la réduction en une seule opération.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant compte les occurrences de mots dans des fichiers. Il utilise [std::vector](vector%20Class.md) pour représenter le contenu de deux fichiers. L'opération de mappage calcule les occurrences de chaque mot dans chaque vecteur. L'opération de réduction cumule le nombre de mots dans les deux vecteurs.  
  
 [!code-cpp[concrt-parallel-map-reduce#1](../../parallel/concrt/codesnippet/CPP/how-to-perform-map-and-reduce-operations-in-parallel_1.cpp)]  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Pour compiler le code, copiez-le et collez-le dans un projet Visual Studio ou collez-le dans un fichier nommé `parallel-map-reduce.cpp` puis exécutez la commande suivante dans une fenêtre d’invite de commandes Visual Studio.  
  
 **CL.exe /EHsc parallèle-map-reduce.cpp**  
  
## <a name="robust-programming"></a>Programmation fiable  
 Dans cet exemple, vous pouvez utiliser la classe `concurrent_unordered_map` (définie dans concurrent_unordered_map.h) pour effectuer le mappage et la réduction en une seule opération.  
  
 [!code-cpp[concrt-parallel-map-reduce#2](../../parallel/concrt/codesnippet/CPP/how-to-perform-map-and-reduce-operations-in-parallel_2.cpp)]  
  
 En règle générale, vous parallélisez uniquement la boucle externe ou interne. Parallélisez la boucle interne si le nombre de fichiers est relativement petit et que chaque fichier contient beaucoup de mots. Parallélisez la boucle externe si le nombre de fichiers est relativement élevé et que chaque fichier contient peu de mots.  
  
## <a name="see-also"></a>Voir aussi  
 [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)   
 [parallel_transform, fonction](../Topic/parallel_transform%20Function.md)   
 [parallel_reduce (fonction)](../Topic/parallel_reduce%20Function.md)   
 [concurrent_unordered_map, classe](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
