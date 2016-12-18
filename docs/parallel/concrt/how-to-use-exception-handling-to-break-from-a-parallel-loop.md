---
title: "Comment&#160;: utiliser la gestion des exceptions pour rompre une boucle parall&#232;le | Microsoft Docs"
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
  - "algorithme de recherche, écrire [runtime d’accès concurrentiel]"
  - "écrire un algorithme de recherche (runtime d'accès concurrentiel)"
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
caps.latest.revision: 15
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: utiliser la gestion des exceptions pour rompre une boucle parall&#232;le
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique indique comment écrire un algorithme de recherche pour une arborescence de base.  
  
 La rubrique [Annulation](../../parallel/concrt/cancellation-in-the-ppl.md) explique le rôle de l'annulation dans la Bibliothèque de modèles parallèles.  Pour annuler un travail parallèle, utiliser la gestion des exceptions est moins efficace que d'utiliser les méthodes [concurrency::task\_group::cancel](../Topic/task_group::cancel%20Method.md) et [concurrency::structured\_task\_group::cancel](../Topic/structured_task_group::cancel%20Method.md).  Toutefois, l'utilisation de la gestion des exceptions pour annuler un travail est adaptée dans le scénario suivant : lorsque vous appelez une bibliothèque tierce qui utilise des tâches ou des algorithmes parallèles, mais qui ne fournit pas d'objet `task_group` ou `structured_task_group` à annuler.  
  
## Exemple  
 L'exemple suivant montre un type `tree` de base qui contient un élément de données et une liste de nœuds enfants.  La section suivante montre le corps de la méthode `for_all`, qui exécute une fonction de travail de manière récursive sur chaque nœud enfant.  
  
 [!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/CPP/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]  
  
## Exemple  
 L'exemple suivant illustre la méthode `for_all`.  Il utilise l'algorithme [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) pour exécuter une fonction de travail sur chaque nœud de l'arborescence en parallèle.  
  
 [!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/CPP/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]  
  
## Exemple  
 L'exemple suivant illustre la fonction `search_for_value`, qui recherche une valeur dans l'objet `tree` fourni.  Cette fonction passe à la méthode `for_all` une fonction de travail qui lève une exception lorsqu'elle détecte un nœud d'arborescence qui contient la valeur fournie.  
  
 Supposez que la classe `tree` est fournie par une bibliothèque tierce et que vous ne pouvez pas la modifier.  Dans ce cas, l'utilisation de la gestion des exceptions est appropriée, car la méthode `for_all` ne fournit pas d'objet `task_group` ou `structured_task_group` à l'appelant.  Par conséquent, la fonction de travail est incapable d'annuler directement son groupe de tâches parent.  
  
 Lorsque la fonction de travail que vous fournissez à un groupe de tâches lève une exception, le runtime arrête toutes les tâches qui sont dans le groupe de tâches \(y compris les groupes de tâches enfants\) et ignore les tâches qui n'ont pas encore démarré.  La fonction `search_for_value` utilise un bloc `try`\-`catch` pour capturer l'exception et imprimer le résultat sur la console.  
  
 [!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/CPP/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]  
  
## Exemple  
 L'exemple suivant crée un objet `tree` et recherche plusieurs valeurs en parallèle dans cet objet.  La fonction `build_tree` est illustrée plus loin dans cette rubrique.  
  
 [!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/CPP/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]  
  
 This example uses the [concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md) algorithm to search for values in parallel.  Pour plus d'informations sur cet algorithme, consultez [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  
  
## Exemple  
 L'exemple complet suivant utilise la gestion des exceptions pour rechercher des valeurs dans une arborescence de base.  
  
 [!code-cpp[concrt-task-tree-search#5](../../parallel/concrt/codesnippet/CPP/how-to-use-exception-handling-to-break-from-a-parallel-loop_5.cpp)]  
  
 Cet exemple génère l'exemple de sortie suivant.  
  
  **Trouvé un nœud avec la valeur 32614.**  
**Trouvé un nœud avec la valeur 86131.**  
**N'a pas trouvé le nœud avec la valeur 17522.**   
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio, ou collez\-le dans un fichier nommé `task-tree-search.cpp` puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio .  
  
 **cl.exe \/EHsc task\-tree\-search.cpp**  
  
## Voir aussi  
 [Annulation](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [Gestion des exceptions](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)   
 [task\_group, classe](../Topic/task_group%20Class.md)   
 [structured\_task\_group, classe](../../parallel/concrt/reference/structured-task-group-class.md)   
 [parallel\_for\_each, fonction](../Topic/parallel_for_each%20Function.md)