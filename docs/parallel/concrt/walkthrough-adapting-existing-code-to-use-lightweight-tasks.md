---
title: "Proc&#233;dure pas &#224; pas&#160;: adaptation d’un code existant pour l’utilisation de t&#226;ches l&#233;g&#232;res | Microsoft Docs"
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
  - "utiliser des tâches légères [Runtime d’accès concurrentiel]"
  - "tâches légères, utiliser [Runtime d’accès concurrentiel]"
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Proc&#233;dure pas &#224; pas&#160;: adaptation d’un code existant pour l’utilisation de t&#226;ches l&#233;g&#232;res
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique indique comment adapter du code existant qui utilise l'API Windows pour créer et exécuter un thread de façon à utiliser une tâche légère.  
  
 Une *tâche légère* est une tâche que vous planifiez directement à partir d'un objet [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) ou [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md).  Les tâches légères sont utiles lorsque vous adaptez du code existant de façon à utiliser les fonctionnalités de planification du runtime d'accès concurrentiel.  
  
## Composants requis  
 Avant de démarrer cette procédure pas à pas, lisez la rubrique [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
## Exemple  
  
### Description  
 L'exemple suivant illustre une utilisation typique de l'API Windows pour créer et exécuter un thread.  Cet exemple utilise la fonction [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) pour appeler `MyThreadFunction` sur un thread séparé.  
  
### Code  
 [!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]  
  
### Commentaires  
 Cet exemple génère la sortie suivante.  
  
  **Paramètres \= 50, 100** Les étapes suivantes indiquent comment adapter l'exemple de code de façon à utiliser le runtime d'accès concurrentiel pour effectuer la même tâche.  
  
### Pour adapter l'exemple de façon à utiliser une tâche légère  
  
1.  Ajoutez une directive `#include` pour le fichier d'en\-tête concrt.h.  
  
     [!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]  
  
2.  Ajoutez une directive `using` pour l'espace de noms `concurrency`.  
  
     [!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]  
  
3.  Modifiez la déclaration de `MyThreadFunction` de façon à utiliser la convention d'appel `__cdecl` et à retourner `void`.  
  
     [!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]  
  
4.  Modifiez la structure `MyData` de façon à inclure un objet [concurrency::event](../../parallel/concrt/reference/event-class.md) qui signale à l'application principale que la tâche est terminée.  
  
     [!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]  
  
5.  Remplacez l'appel à `CreateThread` par un appel à la méthode [concurrency::CurrentScheduler::ScheduleTask](../Topic/CurrentScheduler::ScheduleTask%20Method.md).  
  
     [!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]  
  
6.  Remplacez l'appel à `WaitForSingleObject` par un appel à la méthode [concurrency::event::wait](../Topic/event::wait%20Method.md) pour attendre que la tâche se termine.  
  
     [!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]  
  
7.  Supprimez l'appel à `CloseHandle`.  
  
8.  Modifiez la signature de la définition de `MyThreadFunction` de sorte qu'elle corresponde à l'étape 3.  
  
     [!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]  
  
9. À la fin de la fonction `MyThreadFunction`, appelez la méthode [concurrency::event::set](../Topic/event::set%20Method.md) pour signaler à l'application principale que la tâche est terminée.  
  
     [!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]  
  
10. Supprimez l'instruction `return` de `MyThreadFunction`.  
  
## Exemple  
  
### Description  
 L'exemple complet suivant montre du code qui utilise une tâche légère pour appeler la fonction `MyThreadFunction`.  
  
### Code  
 [!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]  
  
### Commentaires  
  
## Voir aussi  
 [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Scheduler, classe](../../parallel/concrt/reference/scheduler-class.md)