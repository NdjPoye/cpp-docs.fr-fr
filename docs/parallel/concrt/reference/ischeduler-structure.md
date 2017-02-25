---
title: "IScheduler, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IScheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IScheduler (structure)"
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# IScheduler, structure
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Interface à une abstraction d'un planificateur de travail.  Le Gestionnaire des ressources du runtime d'accès concurrentiel utilise cette interface pour communiquer avec les planificateurs de tâches.  
  
## Syntaxe  
  
```  
struct IScheduler;  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IScheduler::AddVirtualProcessors, méthode](../Topic/IScheduler::AddVirtualProcessors%20Method.md)|Fournit un planificateur avec un ensemble de racines de processeur virtuel pour son utilisation.  Chaque interface `IVirtualProcessorRoot` représente le droit d'exécuter un thread unique qui peut exécuter un travail de la part du planificateur.|  
|[IScheduler::GetId, méthode](../Topic/IScheduler::GetId%20Method.md)|Retourne un identificateur unique pour le planificateur.|  
|[IScheduler::GetPolicy, méthode](../Topic/IScheduler::GetPolicy%20Method.md)|Retourne une copie de la stratégie du planificateur.  Pour plus d'informations sur les stratégies de planificateur, consultez [SchedulerPolicy](../../../parallel/concrt/reference/schedulerpolicy-class.md).|  
|[IScheduler::NotifyResourcesExternallyBusy, méthode](../Topic/IScheduler::NotifyResourcesExternallyBusy%20Method.md)|Notifie ce planificateur que les threads matériels représentés par l'ensemble de racines de processeur virtuel du tableau `ppVirtualProcessorRoots` est maintenant utilisé par d'autres planificateurs.|  
|[IScheduler::NotifyResourcesExternallyIdle, méthode](../Topic/IScheduler::NotifyResourcesExternallyIdle%20Method.md)|Notifie ce planificateur que les threads matériels représentés par l'ensemble de racines de processeur virtuel du tableau `ppVirtualProcessorRoots` n'est pas utilisé par d'autres planificateurs.|  
|[IScheduler::RemoveVirtualProcessors, méthode](../Topic/IScheduler::RemoveVirtualProcessors%20Method.md)|Initialise la suppression des racines de processeur virtuel allouées précédemment à ce planificateur.|  
|[IScheduler::Statistics, méthode](../Topic/IScheduler::Statistics%20Method.md)|Fournit des informations relatives à l'arrivée des tâches et au taux de réussite ainsi qu'aux modifications de longueur de file d'attente d'un planificateur.|  
  
## Notes  
 Si vous implémentez un planificateur personnalisé qui communique avec le Gestionnaire de ressources, vous devez fournir une implémentation de l'interface `IScheduler`.  Cette interface est une extrémité d'un canal bidirectionnel de communication entre un planificateur et le Gestionnaire des ressources.  L'autre extrémité est représentée par les interfaces `IResourceManager` et `ISchedulerProxy` implémentées par le Gestionnaire des ressources.  
  
## Hiérarchie d'héritage  
 `IScheduler`  
  
## Configuration requise  
 **En\-tête :** concrtrm.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [PolicyElementKey, énumération](../Topic/PolicyElementKey%20Enumeration.md)   
 [SchedulerPolicy, classe](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [IExecutionContext, structure](../../../parallel/concrt/reference/iexecutioncontext-structure.md)   
 [IThreadProxy, structure](../../../parallel/concrt/reference/ithreadproxy-structure.md)   
 [IVirtualProcessorRoot, structure](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)   
 [IResourceManager, structure](../../../parallel/concrt/reference/iresourcemanager-structure.md)