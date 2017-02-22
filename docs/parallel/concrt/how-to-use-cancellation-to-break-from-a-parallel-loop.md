---
title: "Comment&#160;: utiliser l&#39;annulation pour rompre une boucle parall&#232;le | Microsoft Docs"
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
  - "algorithme de recherche parallèle, écrire (runtime d'accès concurrentiel)"
  - "écrire un algorithme de recherche parallèle (runtime d'accès concurrentiel)"
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Comment&#160;: utiliser l&#39;annulation pour rompre une boucle parall&#232;le
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet exemple indique comment utiliser l'annulation pour implémenter un algorithme basique de recherche parallèle.  
  
## Exemple  
 L'exemple suivant utilise l'annulation pour rechercher un élément dans un tableau.  La fonction `parallel_find_any` utilise l'algorithme [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) et la fonction [concurrency::run\_with\_cancellation\_token](../Topic/run_with_cancellation_token%20Function.md) pour rechercher la position qui contient la valeur donnée.  Lorsque la boucle parallèle recherche la valeur, elle appelle la méthode [concurrency::cancellation\_token\_source::cancel](../Topic/cancellation_token_source::cancel%20Method.md) pour annuler les travaux à venir.  
  
 [!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/CPP/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]  
  
 L'algorithme [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) agit de manière simultanée.  Par conséquent, il n'effectue pas les opérations dans un ordre prédéterminé.  Si le tableau contient plusieurs instances de la valeur, le résultat peut être n'importe laquelle de ses positions.  
  
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet `Visual Studio`, ou collez\-le dans un fichier nommé parallel\-array\-search.cpp puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc parallel\-array\-search.cpp**  
  
## Voir aussi  
 [Annulation](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)   
 [parallel\_for, fonction](../Topic/parallel_for%20Function.md)   
 [cancellation\_token\_source, classe](../../parallel/concrt/reference/cancellation-token-source-class.md)