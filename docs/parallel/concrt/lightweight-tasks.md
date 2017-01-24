---
title: "T&#226;ches l&#233;g&#232;res | Microsoft Docs"
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
  - "tâches légères"
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
caps.latest.revision: 7
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# T&#226;ches l&#233;g&#232;res
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document décrit le rôle des tâches légères dans le runtime d'accès concurrentiel.  Une *tâche légère* est une tâche que vous planifiez directement à partir d'un objet `concurrency::Scheduler` ou `concurrency::ScheduleGroup`.  Une tâche légère s'apparente à la fonction que vous fournissez à la fonction [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) d'API Windows.  Par conséquent, les tâches légères sont utiles lorsque vous adaptez du code existant de façon à utiliser les fonctionnalités de planification du runtime d'accès concurrentiel.  Le runtime d'accès concurrentiel lui\-même utilise des tâches légères pour planifier des agents asynchrones et envoyer des messages entre des blocs de messages asynchrones.  
  
> [!TIP]
>  Le runtime d'accès concurrentiel fournit un planificateur par défaut. Par conséquent, vous n'êtes pas tenu d'en créer un dans votre application.  Étant donné que le planificateur de tâches vous aide à affiner les performances de vos applications, nous vous recommandons de commencer avec la [Bibliothèque de modèles parallèles](../../parallel/concrt/parallel-patterns-library-ppl.md) ou la [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md) si vous ne connaissez pas encore le runtime d'accès concurrentiel.  
  
 Les tâches légères présentent des charges inférieures à celles des agents asynchrones et des groupes de tâches.  Par exemple, le runtime ne vous informe pas lorsqu'une tâche légère se termine.  De plus, il n'intercepte pas et ne gère pas les exceptions levées à partir d'une tâche légère.  Pour plus d'informations sur la gestion des exceptions et les tâches légères, consultez [Gestion des exceptions](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Pour la plupart des tâches, nous vous recommandons d'utiliser des fonctionnalités plus fiables telles que les groupes de tâches et les algorithmes parallèles, car elles simplifient la division de tâches complexes en tâches plus simples.  Pour plus d'informations sur les groupes de tâches, consultez [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  Pour plus d'informations sur les algorithmes parallèles, consultez [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  
  
 Pour créer une tâche légère, appelez les méthodes [concurrency::ScheduleGroup::ScheduleTask](../Topic/ScheduleGroup::ScheduleTask%20Method.md), [concurrency::CurrentScheduler::ScheduleTask](../Topic/CurrentScheduler::ScheduleTask%20Method.md) ou [concurrency::Scheduler::ScheduleTask](../Topic/Scheduler::ScheduleTask%20Method.md).  Pour attendre qu'une tâche légère se termine, attendez que le planificateur parent s'arrête ou utilisez un mécanisme de synchronisation tel qu'un objet [concurrency::event](../../parallel/concrt/reference/event-class.md).  
  
## Exemple  
 Pour obtenir un exemple qui illustre comment adapter du code existant de façon à utiliser une tâche légère, consultez [Procédure pas à pas : adaptation d’un code existant pour l’utilisation de tâches légères](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md).  
  
## Voir aussi  
 [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Procédure pas à pas : adaptation d’un code existant pour l’utilisation de tâches légères](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)