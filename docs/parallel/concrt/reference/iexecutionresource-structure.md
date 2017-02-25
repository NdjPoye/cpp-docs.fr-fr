---
title: "IExecutionResource, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IExecutionResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IExecutionResource (structure)"
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# IExecutionResource, structure
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Abstraction d'un thread matériel.  
  
## Syntaxe  
  
```  
struct IExecutionResource;  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IExecutionResource::CurrentSubscriptionLevel, méthode](../Topic/IExecutionResource::CurrentSubscriptionLevel%20Method.md)|Retourne le nombre de racines de processeur virtuel activées et de threads externes abonnés associés actuellement au thread matériel sous\-jacent que cette ressource d'exécution représente.|  
|[IExecutionResource::GetExecutionResourceId, méthode](../Topic/IExecutionResource::GetExecutionResourceId%20Method.md)|Retourne un identificateur unique pour le thread matériel que cette ressource d'exécution représente.|  
|[IExecutionResource::GetNodeId, méthode](../Topic/IExecutionResource::GetNodeId%20Method.md)|Retourne un identificateur unique pour le nœud processeur auquel cette ressource d'exécution appartient.|  
|[IExecutionResource::Remove, méthode](../Topic/IExecutionResource::Remove%20Method.md)|Retourne cette ressource d'exécution au Gestionnaire de ressources.|  
  
## Notes  
 Les ressources d'exécution peuvent être autonomes ou associées aux racines de processeur virtuel.  Une ressource d'exécution autonome est créée lorsqu'un thread dans votre application crée un abonnement de thread.  Les méthodes [ISchedulerProxy::SubscribeThread](../Topic/ISchedulerProxy::SubscribeCurrentThread%20Method.md) et [ISchedulerProxy::RequestInitialVirtualProcessors](../Topic/ISchedulerProxy::RequestInitialVirtualProcessors%20Method.md) créent des abonnements de thread et retournent une interface `IExecutionResource` qui représente l'abonnement.  La création d'un abonnement de thread constitue une méthode pour informer le Gestionnaire des ressources qu'un thread donné participera au travail mis en file d'attente dans un planificateur, avec les racines de processeur virtuel assignées par le Gestionnaire des ressources au planificateur.  Le Gestionnaire des ressources utilise ces informations pour éviter le surabonnement de threads matériels lorsqu'il le peut.  
  
## Hiérarchie d'héritage  
 `IExecutionResource`  
  
## Configuration requise  
 **En\-tête :** concrtrm.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IVirtualProcessorRoot, structure](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)   
 [ISchedulerProxy::SubscribeCurrentThread, méthode](../Topic/ISchedulerProxy::SubscribeCurrentThread%20Method.md)   
 [ISchedulerProxy::RequestInitialVirtualProcessors, méthode](../Topic/ISchedulerProxy::RequestInitialVirtualProcessors%20Method.md)