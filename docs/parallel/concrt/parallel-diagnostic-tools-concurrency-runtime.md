---
title: "Outils de diagnostic parall&#232;les (runtime d&#39;acc&#232;s concurrentiel) | Microsoft Docs"
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
  - "outils de diagnostic parallèles (runtime d'accès concurrentiel)"
ms.assetid: b1a3f1d2-f5df-4f29-852e-906b3d8341fc
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Outils de diagnostic parall&#232;les (runtime d&#39;acc&#232;s concurrentiel)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] fournit une prise en charge étendue du débogage et du profilage d'applications multithread.  
  
## Débogage  
 Le débogueur Visual Studio inclut la fenêtre **Piles parallèles**, la fenêtre **Tâches en parallèle**, et la fenêtre **Espion parallèle**.  Pour plus d’informations, consultez [Procédure pas à pas : débogage d'une application parallèle](../Topic/Walkthrough:%20Debugging%20a%20Parallel%20Application.md) et [Comment : utiliser la fenêtre Espion parallèle](../Topic/How%20to:%20Use%20the%20Parallel%20Watch%20Window.md).  
  
## Profilage  
 Les outils de profilage fournissent trois vues de données qui affichent des informations graphiques, tabulaires et numériques concernant la manière dont une application multithread interagit avec elle\-même et avec d'autres programmes.  Les vues vous permettent d'identifier rapidement les zones à problème et de naviguer à partir de points sur les affichages graphiques vers des piles d'appels, des sites d'appels et du code source.  Pour plus d'informations, consultez [Visualiseur concurrence](../Topic/Concurrency%20Visualizer.md).  
  
## Suivi d'événements  
 Le runtime d'accès concurrentiel utilise le [Suivi d'événements pour Windows](http://msdn.microsoft.com/library/windows/desktop/bb968803) \(ETW\) pour informer les outils d'instrumentation, tels que les profileurs, lorsque certains événements se produisent.  Il peut notamment s'agir des événements suivants : lorsqu'un planificateur est activé ou désactivé, lorsqu'un contexte commence, se termine, se bloque, se débloque ou cède, et lorsqu'un algorithme parallèle commence ou se termine.  
  
 Les outils, tel que le [Visualiseur concurrence](../Topic/Concurrency%20Visualizer.md), utilisent cette fonctionnalité. Par conséquent, vous ne devez généralement pas utiliser ces événements directement.  Toutefois, ces événements sont utiles lorsque vous développez un profileur personnalisé ou lorsque vous utilisez des outils de suivi d'événements, tel que [Xperf](http://go.microsoft.com/fwlink/?LinkID=160628).  
  
 Le runtime d'accès concurrentiel déclenche ces événements uniquement lorsque le suivi est activé.  Appelez la fonction [concurrency::EnableTracing](../Topic/EnableTracing%20Function.md) pour activer le suivi d'événements et la fonction [concurrency::DisableTracing](../Topic/DisableTracing%20Function.md) pour désactiver le suivi.  
  
 Le tableau suivant décrit les événements que le runtime déclenche lorsque le suivi d'événements est activé :  
  
|Événement|Description|Valeur|  
|---------------|-----------------|------------|  
|[concurrency::ConcRT\_ProviderGuid](../Topic/ConcRT_ProviderGuid%20Constant.md)|Identificateur du fournisseur ETW pour le runtime d'accès concurrentiel.|`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|  
|[concurrency::ContextEventGuid](../Topic/ContextEventGuid%20Constant.md)|Marque les événements qui sont associés aux contextes.|`5727a00f-50be-4519-8256-f7699871fecb`|  
|[concurrency::PPLParallelForEventGuid](../Topic/PPLParallelForEventGuid%20Constant.md)|Marque le début et la fin des appels à l'algorithme [concurrency::parallel\_for](../Topic/parallel_for%20Function.md).|`31c8da6b-6165-4042-8b92-949e315f4d84`|  
|[concurrency::PPLParallelForeachEventGuid](../Topic/PPLParallelForeachEventGuid%20Constant.md)|Marque le début et la fin des appels à l'algorithme [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md).|`5cb7d785-9d66-465d-bae1-4611061b5434`|  
|[concurrency::PPLParallelInvokeEventGuid](../Topic/PPLParallelInvokeEventGuid%20Constant.md)|Marque le début et la fin des appels à l'algorithme [concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md).|`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|  
|[concurrency::SchedulerEventGuid](../Topic/SchedulerEventGuid%20Constant.md)|Marque les événements qui sont associés au [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md).|`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|  
|[concurrency::VirtualProcessorEventGuid](../Topic/VirtualProcessorEventGuid%20Constant.md)|Marque les événements qui sont associés aux processeurs virtuels.|`2f27805f-1676-4ecc-96fa-7eb09d44302f`|  
  
 Le runtime d'accès concurrentiel définit, mais ne déclenche pas pour l'instant, les événements suivants.  Le runtime réserve ces événements pour une utilisation ultérieure :  
  
-   [concurrency::ConcRTEventGuid](../Topic/ConcRTEventGuid%20Constant.md)  
  
-   [concurrency::ScheduleGroupEventGuid](../Topic/SchedulerEventGuid%20Constant.md)  
  
-   [concurrency::ChoreEventGuid](../Topic/ChoreEventGuid%20Constant.md)  
  
-   [concurrency::LockEventGuid](../Topic/LockEventGuid%20Constant.md)  
  
-   [concurrency::ResourceManagerEventGuid](../Topic/ResourceManagerEventGuid%20Constant.md)  
  
 L'énumération [concurrency::ConcRT\_EventType](../Topic/ConcRT_EventType%20Enumeration.md) spécifie les opérations qu'un événement peut suivre.  Par exemple, au début de l'algorithme `parallel_for`, le runtime déclenche l'événement `PPLParallelForEventGuid` et fournit `CONCRT_EVENT_START` en tant qu'opération.  Avant que l'algorithme `parallel_for` retourne une valeur, le runtime déclenche à nouveau l'événement `PPLParallelForEventGuid` et fournit `CONCRT_EVENT_END` en tant qu'opération.  
  
 L'exemple suivant montre comment activer le suivi pour un appel à `parallel_for`.  Le runtime n'effectue pas le suivi du premier appel à `parallel_for` car le suivi n'est pas activé.  L'appel à `EnableTracing` permet au runtime d'effectuer le suivi du deuxième appel à `parallel_for`.  
  
 [!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/CPP/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]  
  
 Le runtime assure le suivi du nombre de fois que vous appelez `EnableTracing` et `DisableTracing`.  Par conséquent, si vous appelez `EnableTracing` plusieurs fois, vous devez appeler `DisableTracing` le même nombre de fois pour désactiver le suivi.  
  
## Voir aussi  
 [Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)