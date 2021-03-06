---
title: 'Comment : utiliser des exceptions pour rompre une boucle parallèle | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- search algorithm, writing [Concurrency Runtime]
- writing a search algorithm [Concurrency Runtime]
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6bacb9ea6a451026f7a515878cb649090ed9cbf4
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-exception-handling-to-break-from-a-parallel-loop"></a>Comment : utiliser la gestion des exceptions pour rompre une boucle parallèle
Cette rubrique montre comment écrire un algorithme de recherche pour une arborescence de base.  
  
 La rubrique [annulation](cancellation-in-the-ppl.md) explique le rôle de l’annulation dans la bibliothèque de modèles parallèles. L’utilisation de la gestion des exceptions est moins efficace pour annuler un travail parallèle que l’utilisation de la [Concurrency::task_group :: Cancel](reference/task-group-class.md#cancel) et [Concurrency::structured_task_group :: Cancel](reference/structured-task-group-class.md#cancel) méthodes. Toutefois, un scénario dans lequel l’utilisation de la gestion des exceptions pour annuler un travail est appropriée est quand vous appelez une bibliothèque tierce qui utilise des tâches ou des algorithmes parallèles, mais ne fournit pas un `task_group` ou `structured_task_group` objet à annuler.  

  
## <a name="example"></a>Exemple  
 L’exemple suivant montre un basic `tree` type qui contient un élément de données et une liste de nœuds enfants. La section suivante montre le corps de la `for_all` méthode, qui exécute manière récursive une fonction de travail sur chaque nœud enfant.  
  
 [!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre le `for_all` (méthode). Elle utilise le [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algorithme pour effectuer une fonction de travail sur chaque nœud de l’arborescence en parallèle.  
  
 [!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]  
  
## <a name="example"></a>Exemple  
 L'exemple suivant illustre la fonction `search_for_value`, qui recherche une valeur dans l'objet `tree` fourni. Cette fonction passe à la `for_all` méthode une fonction de travail qui lève lorsqu’elle détecte un nœud d’arborescence qui contient la valeur fournie.  
  
 Supposons que la `tree` classe est fournie par une bibliothèque tierce et que vous ne pouvez pas le modifier. Dans ce cas, l’utilisation de la gestion des exceptions est appropriée, car le `for_all` ne fournit pas de méthode un `task_group` ou `structured_task_group` objet à l’appelant. Par conséquent, la fonction de travail ne peut pas annuler directement son groupe de tâches parent.  
  
 Lorsque la fonction de travail que vous fournissez à un groupe de tâches lève une exception, le runtime arrête toutes les tâches qui se trouvent dans le groupe de tâches (y compris les groupes de tâches enfants) et ignore les tâches qui n’ont pas encore démarré. Le `search_for_value` fonction utilise un `try` - `catch` bloc pour capturer l’exception et imprimer le résultat dans la console.  
  
 [!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]  
  
## <a name="example"></a>Exemple  
 L’exemple suivant crée un `tree` de l’objet et de recherche pour plusieurs valeurs en parallèle. Le `build_tree` fonction est illustrée plus loin dans cette rubrique.  
  
 [!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]  
  
 Cet exemple utilise le [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algorithme pour rechercher des valeurs en parallèle. Pour plus d’informations sur cet algorithme, consultez [des algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="example"></a>Exemple  
 L’exemple complet suivant utilise la gestion des exceptions pour rechercher des valeurs dans une arborescence de base.  
  
 [!code-cpp[concrt-task-tree-search#5](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_5.cpp)]  
  
 Cet exemple génère la sortie suivante.  
  
```Output  
Found a node with value 32614.  
Found a node with value 86131.  
Did not find node with value 17522.  
```  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Copiez l’exemple de code et collez-le dans un projet Visual Studio ou collez-le dans un fichier nommé `task-tree-search.cpp` , puis exécutez la commande suivante dans une fenêtre d’invite de commandes Visual Studio.  
  
 **/EHsc CL.exe task-tree-search.cpp**  
  
## <a name="see-also"></a>Voir aussi  
 [Annulation dans la bibliothèque de modèles parallèles](cancellation-in-the-ppl.md)   
 [Gestion des exceptions](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)   
 [task_group, classe](reference/task-group-class.md)   
 [structured_task_group, classe](../../parallel/concrt/reference/structured-task-group-class.md)   
 [parallel_for_each, fonction](reference/concurrency-namespace-functions.md#parallel_for_each)


