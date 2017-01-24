---
title: "Strat&#233;gies de planificateur | Microsoft Docs"
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
  - "stratégies de planificateur"
ms.assetid: 58fb68bd-4a57-40a8-807b-6edb6f083cd9
caps.latest.revision: 12
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Strat&#233;gies de planificateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document décrit le rôle des stratégies du planificateur dans le runtime d'accès concurrentiel.  Une *stratégie du planificateur* contrôle la stratégie utilisée par le planificateur lorsqu'il gère des tâches.  Par exemple, considérez une requête qui nécessite des tâches à exécuter sur `THREAD_PRIORITY_NORMAL` et d'autres tâches à exécuter sur `THREAD_PRIORITY_HIGHEST`.  Vous pouvez créer deux instances du planificateur : un qui spécifie la stratégie `ContextPriority` pour être `THREAD_PRIORITY_NORMAL` et un autre qui spécifient la même stratégie pour être `THREAD_PRIORITY_HIGHEST`.  
  
 En utilisant les stratégies du planificateur, vous pouvez répartir les ressources de traitement disponibles et assigner un jeu fixe de ressources à chaque planificateur.  Par exemple, imaginez un algorithme parallèle qui ne peut pas monter en charge au\-delà de quatre processeurs.  Vous pouvez alors créer une stratégie de planificateur qui limite ses tâches de façon à ne pas utiliser plus de quatre processeurs simultanément.  
  
> [!TIP]
>  Le runtime d'accès concurrentiel fournit un planificateur par défaut.  Par conséquent, vous n'avez pas à en créer un dans votre application.  Étant donné que le planificateur de tâches vous aide à affiner les performances de vos applications, nous vous recommandons de commencer avec la [Bibliothèque de modèles parallèles](../../parallel/concrt/parallel-patterns-library-ppl.md) ou la [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md) si vous ne connaissez pas encore le runtime d'accès concurrentiel.  
  
 Lorsque vous utilisez la méthode [concurrency::CurrentScheduler::Create](../Topic/CurrentScheduler::Create%20Method.md), [concurrency::Scheduler::Create](../Topic/Scheduler::Create%20Method.md) ou [concurrency::Scheduler::SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md) pour créer une instance du planificateur, vous fournissez un objet [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) qui contient une collection de paires clé\/valeur qui spécifie le comportement du planificateur.  Le constructeur `SchedulerPolicy` prend un nombre variable d'arguments.  Le premier argument est le nombre d'éléments de stratégie que vous allez spécifier.  Les arguments restants sont des paires clé\-valeur pour chaque élément de stratégie.  L'exemple suivant crée un objet `SchedulerPolicy` qui spécifie trois éléments de stratégie.  Le runtime utilise des valeurs par défaut pour les clés de stratégie qui ne sont pas spécifiées.  
  
 [!code-cpp[concrt-scheduler-policy#2](../../parallel/concrt/codesnippet/CPP/scheduler-policies_1.cpp)]  
  
 L'énumération [concurrency::PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md) définit les clés de stratégie associées au Planificateur de tâches.  Le tableau suivant décrit les clés de stratégie ainsi que la valeur par défaut que le runtime utilise pour chacune d'elles.  
  
|Clé de stratégie|Description|Valeur par défaut|  
|----------------------|-----------------|-----------------------|  
|`SchedulerKind`|Valeur [concurrency::SchedulerType](../Topic/SchedulerType%20Enumeration.md) qui spécifie le type de threads normaux utiliser pour planifier des tâches.|`ThreadScheduler` \(utilisez des threads normaux\).  Il s'agit de la seule valeur valide pour cette clé.|  
|`MaxConcurrency`|Valeur `unsigned int` qui spécifie le nombre maximal de ressources d'accès concurrentiel utilisées par le planificateur.|[concurrency::MaxExecutionResources](../Topic/MaxExecutionResources%20Constant.md)|  
|`MinConcurrency`|Valeur `unsigned int` qui spécifie le nombre minimal de ressources d'accès concurrentiel utilisées par le planificateur.|`1`|  
|`TargetOversubscriptionFactor`|Valeur `unsigned int` qui spécifie le nombre de threads à allouer à chaque ressource de traitement.|`1`|  
|`LocalContextCacheSize`|Valeur `unsigned int` qui spécifie le nombre maximal de contextes qui peuvent être mis en cache dans la file d'attente locale de chaque processeur virtuel.|`8`|  
|`ContextStackSize`|Valeur `unsigned int` qui spécifie la taille de la pile, en kilo\-octets, à réserver pour chaque contexte.|`0` \(utiliser la taille de pile par défaut\)|  
|`ContextPriority`|Valeur `int` qui spécifie la priorité de thread de chaque contexte.  Il peut s'agir de toute valeur que vous pouvez passer à [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) ou `INHERIT_THREAD_PRIORITY`.|`THREAD_PRIORITY_NORMAL`|  
|`SchedulingProtocol`|Une valeur [concurrency::SchedulingProtocolType](../Topic/SchedulingProtocolType%20Enumeration.md) qui spécifie l'algorithme de planification à utiliser.|`EnhanceScheduleGroupLocality`|  
|`DynamicProgressFeedback`|Une valeur [concurrency::DynamicProgressFeedbackType](../Topic/DynamicProgressFeedbackType%20Enumeration.md) qui spécifie s'il faut rééquilibrer les ressources d'après les informations de progression basées sur les statistiques.<br /><br /> **Remarque** Ne définissez pas cette stratégie à `ProgressFeedbackDisabled` car elle est réservée pour être utilisée par le runtime.|`ProgressFeedbackEnabled`|  
  
 Chaque planificateur utilise sa propre stratégie lorsqu'il planifie des tâches.  Par conséquent, les stratégies associées à un planificateur n'affectent le comportement d'aucun autre planificateur.  De plus, vous ne pouvez pas modifier la stratégie du planificateur après avoir créé l'objet `Scheduler`.  
  
> [!IMPORTANT]
>  Utilisez les stratégies du planificateur uniquement pour contrôler les attributs pour les threads créés par le runtime.  La modification de l'affinité ou de la priorité de thread créés par le runtime produit un comportement non défini.  
  
 Le runtime crée un planificateur par défaut à votre place si vous n'en créez pas un explicitement.  Si vous souhaitez utiliser le planificateur par défaut dans votre application, mais que vous souhaitez spécifier une stratégie qui sera utilisée par ce planificateur, appelez la méthode [concurrency::Scheduler::SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md) avant de planifier un travail parallèle.  Si vous n'appelez pas la méthode `Scheduler::SetDefaultSchedulerPolicy`, le runtime utilise les valeurs de stratégie par défaut fournies dans le tableau.  
  
 Utilisez les méthodes [concurrency::CurrentScheduler::GetPolicy](../Topic/CurrentScheduler::GetPolicy%20Method.md) et [concurrency::Scheduler::GetPolicy](../Topic/Scheduler::GetPolicy%20Method.md) pour extraire une copie de la stratégie du planificateur.  Les valeurs de stratégie que vous recevez de ces méthodes peuvent différer des valeurs de stratégie que vous spécifiez lors de la création du planificateur.  
  
## Exemple  
 Pour examiner des exemples qui utilisent des stratégies du planificateur spécifiques pour contrôler le comportement du planificateur, consultez [Comment : spécifier des stratégies de planificateur](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md) et [Comment : créer des agents qui utilisent des stratégies de planificateur spécifiques](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).  
  
## Voir aussi  
 [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Comment : spécifier des stratégies de planificateur](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)   
 [Comment : créer des agents qui utilisent des stratégies de planificateur spécifiques](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)