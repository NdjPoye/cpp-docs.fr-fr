---
title: "Comment&#160;: &#233;crire une boucle parallel_for | Microsoft Docs"
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
  - "écrire une boucle parallel_for (runtime d'accès concurrentiel)"
  - "parallel_for, exemple de fonction"
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
caps.latest.revision: 15
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: &#233;crire une boucle parallel_for
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet exemple montre comment utiliser [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) pour calculer le produit de deux matrices.  
  
## Exemple  
 L'exemple suivant illustre la fonction `matrix_multiply`, qui calcule le produit de deux matrices carrées.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#1](../../parallel/concrt/codesnippet/CPP/how-to-write-a-parallel-for-loop_1.cpp)]  
  
## Exemple  
 L'exemple suivant illustre la fonction `parallel_matrix_multiply`, qui utilise l'algorithme `parallel_for` pour exécuter la boucle externe en parallèle.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#2](../../parallel/concrt/codesnippet/CPP/how-to-write-a-parallel-for-loop_2.cpp)]  
  
 Cet exemple parallélise la boucle externe uniquement car elle exécute suffisamment de travail pour tirer parti de la charge pour le traitement en parallèle.  Si vous parallélisez la boucle interne, vous ne constaterez pas de gain de performances car la petite quantité de travail effectuée par la boucle interne ne justifie pas la charge pour le traitement en parallèle.  Par conséquent, paralléliser uniquement la boucle externe est le meilleur moyen d'optimiser les avantages offerts par l'accès concurrentiel sur la plupart des systèmes.  
  
## Exemple  
 L'exemple suivant plus complet compare les performances de la fonction `matrix_multiply` à celles de la fonction `parallel_matrix_multiply`.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#3](../../parallel/concrt/codesnippet/CPP/how-to-write-a-parallel-for-loop_3.cpp)]  
  
 L'exemple de sortie suivant concerne un ordinateur avec quatre processeurs.  
  
  **série : 3853**  
**Parallel : 1311**   
## Compilation du code  
 Pour compiler le code, copiez\-le puis collez\-le dans un projet Visual Studio , ou collez\-le dans un fichier nommé `parallel-matrix-multiply.cpp` puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc parallel\-matrix\-multiply.cpp**  
  
## Voir aussi  
 [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)   
 [parallel\_for, fonction](../Topic/parallel_for%20Function.md)