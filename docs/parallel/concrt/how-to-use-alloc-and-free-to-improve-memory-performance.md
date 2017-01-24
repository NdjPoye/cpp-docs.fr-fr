---
title: "Comment&#160;: utiliser Alloc et Free pour am&#233;liorer les performances de la m&#233;moire | Microsoft Docs"
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
  - "Alloc et Free, utiliser [Runtime d’accès concurrentiel]"
  - "Utilisation d’Alloc et de Free [Runtime d’accès concurrentiel]"
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
caps.latest.revision: 14
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: utiliser Alloc et Free pour am&#233;liorer les performances de la m&#233;moire
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document indique comment utiliser les fonctions [concurrency::Alloc](../Topic/Alloc%20Function.md) et [concurrency::Free](../Topic/Free%20Function.md) pour améliorer les performances de la mémoire.  Il compare la durée requise pour inverser les éléments d'un tableau en parallèle pour trois types différents qui spécifient chacun les opérateurs `new` et `delete`.  
  
 Les fonctions `Alloc` et `Free` sont le plus utile lorsque plusieurs threads appellent fréquemment `Alloc` et `Free`.  Le runtime maintient un cache mémoire séparé pour chaque thread ; par conséquent, le runtime gère la mémoire sans utiliser de verrous ou de barrières de mémoire.  
  
## Exemple  
 L'exemple suivant illustre trois types qui spécifient chacun les opérateurs `delete` et `new`.  La classe `new_delete` utilise les opérateurs globaux `new` et `delete`, la classe `malloc_free` utilise les fonctions [malloc](../../c-runtime-library/reference/malloc.md) et [free](../../c-runtime-library/reference/free.md) du runtime C, et la classe `Alloc_Free` utilise les fonctions `Alloc` et `Free` du runtime d'accès concurrentiel.  
  
 [!code-cpp[concrt-allocators#1](../../parallel/concrt/codesnippet/CPP/how-to-use-alloc-and-free-to-improve-memory-performance_1.cpp)]  
  
## Exemple  
 L'exemple suivant illustre les fonctions `swap` et `reverse_array`.  La fonction `swap` échange le contenu du tableau aux index spécifiés.  Il alloue la mémoire du tas pour la variable temporaire.  La fonction `reverse_array` crée un grand tableau et calcule la durée requise pour inverser ce tableau plusieurs fois en parallèle.  
  
 [!code-cpp[concrt-allocators#2](../../parallel/concrt/codesnippet/CPP/how-to-use-alloc-and-free-to-improve-memory-performance_2.cpp)]  
  
## Exemple  
 L'exemple suivant illustre la fonction `wmain`, qui calcule la durée requise pour que la fonction `reverse_array` agisse sur les types `new_delete`, `malloc_free` et `Alloc_Free`, qui utilisent chacun une méthode d'allocation de mémoire différente.  
  
 [!code-cpp[concrt-allocators#3](../../parallel/concrt/codesnippet/CPP/how-to-use-alloc-and-free-to-improve-memory-performance_3.cpp)]  
  
## Exemple  
 Voici un exemple de code complet :  
  
 [!code-cpp[concrt-allocators#4](../../parallel/concrt/codesnippet/CPP/how-to-use-alloc-and-free-to-improve-memory-performance_4.cpp)]  
  
 Cet exemple produit l'exemple de sortie suivant pour un ordinateur qui a quatre processeurs.  
  
  **A pris 2031 ms à nouveau\/supprimer.**  
**A nécessité 1672 ms à malloc\/libérer.**  
**A nécessité 656 ms à Allocation\/libérer.** Dans cet exemple, le type qui utilise les fonctions `Alloc` et `Free` procure de meilleures performances de mémoire car les fonctions `Alloc` et `Free` sont optimisées pour l'allocation et la libération fréquentes des blocs de mémoire de plusieurs threads.  
  
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio , ou collez\-le dans un fichier nommé allocators.cpp puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc allocators.cpp**  
  
## Voir aussi  
 [Fonctions de gestion de la mémoire](../../parallel/concrt/memory-management-functions.md)   
 [Alloc, fonction](../Topic/Alloc%20Function.md)   
 [Free, fonction](../Topic/Free%20Function.md)