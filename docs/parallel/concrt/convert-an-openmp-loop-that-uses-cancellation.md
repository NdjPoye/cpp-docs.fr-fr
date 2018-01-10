---
title: "Comment : convertir une boucle OpenMP qui a recours à l’annulation pour utiliser le Runtime d’accès concurrentiel | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, cancellation
- cancellation, converting from OpenMP to the Concurrency Runtime
ms.assetid: 4b0b3c33-bfa9-4e96-ae08-aef245a39cbb
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d3c4d37dfe5182e375e7581d6f5ef8188b922e5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-an-openmp-loop-that-uses-cancellation-to-use-the-concurrency-runtime"></a>Comment : convertir une boucle OpenMP qui a recours à l’annulation pour utiliser le runtime d’accès concurrentiel
Des boucles parallèles ne requièrent pas que toutes les itérations être exécutée. Par exemple, un algorithme qui recherche une valeur peut se terminer dès que la valeur est trouvée. OpenMP ne fournit pas un mécanisme pour sortir d’une boucle parallèle. Toutefois, vous pouvez utiliser une valeur booléenne, ou indicateur, pour permettre à une itération de la boucle pour indiquer que la solution a été trouvée. Le Runtime d’accès concurrentiel fournit des fonctionnalités qui activent une tâche pour annuler d’autres tâches qui n’ont pas encore démarré.  
  
 Cet exemple montre comment convertir une OpenMP [parallèles](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[pour](../../parallel/openmp/reference/for-openmp.md) boucle qui ne requiert pas d’utiliser le mécanisme d’annulation de Runtime d’accès concurrentiel pour toutes les itérations à exécuter.  
  
## <a name="example"></a>Exemple  

 Cet exemple utilise OpenMP et le Runtime d’accès concurrentiel pour implémenter une version parallèle de la [std::any_of](../../standard-library/algorithm-functions.md#any_of) algorithme. La version OpenMP de cet exemple utilise un indicateur pour coordonner toutes les itérations de boucle parallèle que la condition a été remplie. La version qui utilise le Runtime d’accès concurrentiel utilise le [Concurrency::structured_task_group :: Cancel](reference/structured-task-group-class.md#cancel) méthode pour arrêter l’opération globale lorsque la condition est remplie.  

  
 [!code-cpp[concrt-openmp#2](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-cancellation_1.cpp)]  
  
 Cet exemple produit la sortie suivante.  
  
```Output  
Using OpenMP...  
9114046 is in the array.  
Using the Concurrency Runtime...  
9114046 is in the array.  
```  
  
 Dans la version qui utilise OpenMP, toutes les itérations de la boucle s’exécutent, même lorsque l’indicateur est défini. En outre, si une tâche pour que toutes les tâches enfants, l’indicateur également devrait être disponible pour ces tâches enfants pour communiquer l’annulation. Dans le Runtime d’accès concurrentiel, quand un groupe de tâches est annulé, le runtime annule l’ensemble de l’arborescence de travail, y compris les tâches enfants. Le [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algorithme utilise des tâches pour effectuer le travail. Par conséquent, lorsqu’une itération de la boucle annule la tâche racine, l’ensemble de l’arborescence du calcul est également annulé. Lorsqu’une arborescence de travail est annulée, le runtime ne démarre pas de nouvelles tâches. Toutefois, le runtime autorise les tâches que vous ont déjà commencé à terminer. Par conséquent, dans le cas de la `parallel_for_each` algorithme, itérations de boucle active peuvent nettoyer ses ressources.  
  
 Dans les deux versions de cet exemple, si le tableau contient plusieurs copies de la valeur à rechercher, plusieurs itérations de boucle peuvent définir simultanément le résultat et annuler l’opération globale. Vous pouvez utiliser une primitive de synchronisation, tel qu’une section critique, si votre problème ne nécessite qu’une seule tâche effectue un travail lorsqu’une condition est remplie.  
  
 Vous pouvez également utiliser la gestion des exceptions pour annuler des tâches qui utilisent la bibliothèque PPL. Pour plus d’informations sur l’annulation, consultez [l’annulation dans la bibliothèque PPL](cancellation-in-the-ppl.md).  
  
 Pour plus d’informations sur `parallel_for_each` et d’autres algorithmes parallèles, consultez [des algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Copiez l’exemple de code et collez-le dans un projet Visual Studio ou collez-le dans un fichier nommé `concrt-omp-parallel-any-of.cpp` , puis exécutez la commande suivante dans une fenêtre d’invite de commandes Visual Studio.  
  
 **CL.exe /EHsc /openmp concrt-omp-parallèle-any-of.cpp**  
  
## <a name="see-also"></a>Voir aussi  
 [Migration d’OpenMP au Runtime d’accès concurrentiel](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Annulation dans la bibliothèque de modèles parallèles](cancellation-in-the-ppl.md)   
 [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)

