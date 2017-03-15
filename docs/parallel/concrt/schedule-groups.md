---
title: "Groupes de planification | Microsoft Docs"
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
  - "groupes de planification"
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Groupes de planification
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document décrit le rôle de groupes de planification dans le Runtime d’accès concurrentiel. Un *groupe de planification* dont ou regroupe, tâches associées. Chaque planificateur possède un ou plusieurs groupes de planification. Utilisez des groupes de planification quand vous avez besoin d’un degré élevé de localité entre les tâches, par exemple, quand un groupe de tâches connexes tire parti d’une exécution sur le même nœud de processeur. Inversement, utilisez des instances de planificateur lorsque votre application a des exigences de qualité spécifiques, par exemple, lorsque vous souhaitez limiter la quantité de ressources de traitement qui sont allouées à un ensemble de tâches. Pour plus d’informations sur les instances de planificateur, consultez [Instances de planificateur](../../parallel/concrt/scheduler-instances.md).  
  
> [!TIP]
>  Le runtime d'accès concurrentiel fournit un planificateur par défaut, et vous n'êtes donc pas obligé d'en créer un dans votre application. Étant donné que le Planificateur de tâches vous aide à optimiser les performances de vos applications, nous vous recommandons de commencer avec la [bibliothèque de modèles parallèles (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) ou [bibliothèque d’Agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md) Si vous ne connaissez pas le Runtime d’accès concurrentiel.  
  
 Chaque `Scheduler` objet possède un groupe de planification par défaut pour chaque nœud de planification. Un *nœud de planification* est mappé à la topologie de système sous-jacente. Le runtime crée un nœud de planification pour chaque package de processeur ou nœud de l’Architecture de mémoire Non uniforme (NUMA), selon le nombre est supérieur. Si vous n’associez pas explicitement une tâche à un groupe de planification, le planificateur choisit le groupe à ajouter la tâche.  
  
 Le `SchedulingProtocol` Planificateur stratégie détermine l’ordre dans lequel le planificateur exécute les tâches dans chaque groupe de planification. Lorsque `SchedulingProtocol` a la valeur `EnhanceScheduleGroupLocality` (qui est la valeur par défaut), le Planificateur de tâches sélectionne la tâche suivante dans le groupe de planification qui fonctionne sur lorsque la tâche actuelle se termine ou cède de façon coopérative. Le Planificateur de tâches recherche le groupe actuel de la planification de travail avant de passer au groupe disponible suivant. À l’inverse, lorsque `SchedulingProtocol` est défini sur `EnhanceForwardProgress`, le planificateur passe au groupe de planification suivant après chaque tâche. Pour obtenir un exemple qui compare ces stratégies, consultez [Comment : utiliser des groupes de planification pour Influence ordre d’exécution](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  
 Le runtime utilise le [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) classe pour représenter des groupes de planification. Pour créer un `ScheduleGroup` de l’objet, appelez le [Concurrency::CurrentScheduler :: CreateScheduleGroup](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md) ou [Concurrency::Scheduler :: CreateScheduleGroup](../Topic/Scheduler::CreateScheduleGroup%20Method.md) méthode. Le runtime utilise un mécanisme de décompte de références pour contrôler la durée de vie de `ScheduleGroup` des objets, comme il le fait avec `Scheduler` objets. Lorsque vous créez un `ScheduleGroup` de l’objet, le runtime définit la référence un compteur. Le [Concurrency::ScheduleGroup](../Topic/ScheduleGroup::Reference%20Method.md) méthode incrémente le compteur de références d’une unité. Le [Concurrency::ScheduleGroup :: Release](../Topic/ScheduleGroup::Release%20Method.md) méthode décrémente le compteur de références d’un.  
  
 De nombreux types dans le Runtime d’accès concurrentiel vous permettent d’associer un objet à un groupe de planification. Par exemple, le [concurrency::agent](../../parallel/concrt/reference/agent-class.md) classes de bloc de message et de la classe, telles que [concurrency::unbounded_buffer](../Topic/unbounded_buffer%20Class.md), [concurrency::join](../../parallel/concrt/reference/join-class.md), et la concurrence ::[timer](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/d5d4c847-5ad6-4c7f-b35b-d0b6f446d8b4/locales/en-US), fournissent des versions surchargées du constructeur qui prennent un `ScheduleGroup` objet. Le runtime utilise le `Scheduler` qui est associé à cet objet `ScheduleGroup` objet pour planifier la tâche.  
  
 Vous pouvez également utiliser le [Concurrency::ScheduleGroup :: ScheduleTask](../Topic/ScheduleGroup::ScheduleTask%20Method.md) méthode pour planifier une tâche légère. Pour plus d’informations sur les tâches légères, consultez [tâches légères](../../parallel/concrt/lightweight-tasks.md).  
  
## <a name="example"></a>Exemple  
 Pour obtenir un exemple qui utilise des groupes pour contrôler l’ordre d’exécution des tâches de planification, consultez [Comment : utiliser des groupes de planification pour Influence ordre d’exécution](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Instances de planificateur](../../parallel/concrt/scheduler-instances.md)   
 [Comment : utiliser des groupes de planifications pour influencer l’ordre d’exécution](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)

