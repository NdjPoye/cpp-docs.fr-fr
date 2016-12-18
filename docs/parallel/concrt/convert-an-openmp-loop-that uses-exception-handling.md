---
title: "Comment&#160;: convertir une boucle OpenMP qui a recours &#224; la gestion des exceptions pour utiliser le runtime d&#39;acc&#232;s concurrentiel | Microsoft Docs"
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
  - "gestion des exceptions, convertir d’OpenMP au runtime d’accès concurrentiel"
  - "convertir d’OpenMP au runtime d’accès concurrentiel, gestion des exceptions"
ms.assetid: 03c28196-21ba-439e-8641-afab1c283e1a
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: convertir une boucle OpenMP qui a recours &#224; la gestion des exceptions pour utiliser le runtime d&#39;acc&#232;s concurrentiel
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet exemple montre comment convertir une boucle OpenMP [parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md) qui exécute la gestion des exceptions afin d'utiliser le mécanisme de gestion des exceptions du runtime d'accès concurrentiel.  
  
 Dans OpenMP, une exception qui est levée dans une région parallèle doit être interceptée et gérée dans la même région, par le même thread.  Une exception qui échappe à la région parallèle est interceptée par le gestionnaire d'exceptions non gérées, qui, par défaut, met fin au processus.  
  
 Dans le runtime d'accès concurrentiel, lorsque vous levez une exception dans le corps d'une fonction de travail que vous passez à un groupe de tâches, comme l'objet [concurrency::task\_group](../Topic/task_group%20Class.md) ou [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md), ou à un algorithme parallèle comme [concurrency::parallel\_for](../Topic/parallel_for%20Function.md), le runtime stocke cette exception et la guide vers le contexte qui attend que le groupe ou l'algorithme de tâches se termine.  Pour les groupes de tâches, le contexte d'attente est le contexte qui appelle [concurrency::task\_group::wait](../Topic/task_group::wait%20Method.md), [concurrency::structured\_task\_group::wait](../Topic/structured_task_group::wait%20Method.md), [concurrency::task\_group::run\_and\_wait](../Topic/task_group::run_and_wait%20Method.md) ou [concurrency::structured\_task\_group::run\_and\_wait](../Topic/structured_task_group::run_and_wait%20Method.md).  Pour un algorithme parallèle, le contexte d'attente est le contexte qui a appelé cet algorithme.  Le runtime arrête également toutes les tâches actives qui sont dans le groupe de tâches, y compris celles des groupes de tâches enfants, et ignore toutes les tâches qui n'ont pas encore démarré.  
  
## Exemple  
 Cet exemple montre comment gérer des exceptions dans une région `parallel` OpenMP et dans un appel à `parallel_for`.  La fonction `do_work` effectue une demande d'allocation de mémoire qui n'aboutit pas. Elle lève, par conséquent, une exception de type [std::bad\_alloc](../../standard-library/bad-alloc-class.md).  Dans la version qui utilise OpenMP, le thread qui lève l'exception doit également l'intercepter.  En d'autres termes, chaque itération d'une boucle parallèle OpenMP doit gérer l'exception.  Dans la version qui utilise le runtime d'accès concurrentiel, le thread principal intercepte une exception qui est levée par un autre thread.  
  
 [!code-cpp[concrt-openmp#3](../../parallel/concrt/codesnippet/CPP/convert-an-openmp-loop-that uses-exception-handling_1.cpp)]  
  
 Cet exemple génère la sortie suivante.  
  
  **Utilisation de OpenMP…**  
**Une erreur de type «class std::bad\_alloc » s'est produite.**  
**Une erreur de type «class std::bad\_alloc » s'est produite.**  
**Une erreur de type «class std::bad\_alloc » s'est produite.**  
**Une erreur de type «class std::bad\_alloc » s'est produite.**  
**Une erreur de type «class std::bad\_alloc » s'est produite.**  
**Une erreur de type «class std::bad\_alloc » s'est produite.**  
**Une erreur de type «class std::bad\_alloc » s'est produite.**  
**Une erreur de type «class std::bad\_alloc » s'est produite.**  
**Une erreur de type «class std::bad\_alloc » s'est produite.**  
**Une erreur de type «class std::bad\_alloc » s'est produite.**  
**Utilisation du runtime d'accès concurrentiel...**  
**Une erreur de type «classe std::bad\_alloc » s'est produite.** Dans la version de cet exemple qui utilise OpenMP, l'exception se produit dans chaque itération de boucle. Chaque itération gère l'exception.  Dans la version qui utilise le runtime d'accès concurrentiel, le runtime stocke l'exception, arrête toutes les tâches actives, ignore toutes les tâches qui n'ont pas encore commencé et marshale l'exception au contexte qui appelle `parallel_for`.  
  
 Si vous avez besoin que la version qui utilise OpenMP se termine une fois que l'exception s'est produite, vous pouvez utiliser un indicateur booléen pour signaler à d'autres itérations de boucle que l'erreur s'est produite.  Comme dans l'exemple de la rubrique [Comment : convertir une boucle OpenMP qui a recours à l’annulation pour utiliser le runtime d’accès concurrentiel](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md), les itérations de boucle ultérieures n'auront aucun effet si l'indicateur est défini.  En revanche, si vous avez besoin que la boucle qui utilise le runtime d'accès concurrentiel se poursuive une fois que l'exception s'est produite, gérez l'exception dans le corps même de la boucle parallèle.  
  
 D'autres composants du runtime d'accès concurrentiel, tels que les agents asynchrones et les tâches légères, ne transportent pas d'exceptions.  Au lieu de cela, les exceptions non gérées sont interceptées par le gestionnaire d'exceptions non gérées, qui, par défaut, met fin au processus.  Pour plus d'informations sur la gestion des exceptions, consultez [Gestion des exceptions](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Pour plus d'informations sur `parallel_for` et d'autres algorithmes parallèles, consultez [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  
  
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio, ou collez\-le dans un fichier nommé `concrt-omp-exceptions.cpp`. Exécutez ensuite la commande suivante dans une fenêtre d'invite de commandes Visual Studio .  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-exceptions.cpp**  
  
## Voir aussi  
 [Migration d'OpenMP au runtime d'accès concurrentiel](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Gestion des exceptions](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)