---
title: "ISchedulerProxy, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::ISchedulerProxy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISchedulerProxy (structure)"
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# ISchedulerProxy, structure
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Interface par laquelle les planificateurs communiquent avec le Gestionnaire des ressources du runtime d'accès concurrentiel pour négocier l'allocation des ressources.  
  
## Syntaxe  
  
```  
struct ISchedulerProxy;  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ISchedulerProxy::BindContext, méthode](../Topic/ISchedulerProxy::BindContext%20Method.md)|Associe un contexte d'exécution à un proxy de thread, s'il n'est pas déjà associé à un proxy de ce type.|  
|[ISchedulerProxy::CreateOversubscriber, méthode](../Topic/ISchedulerProxy::CreateOversubscriber%20Method.md)|Crée une racine de processeur virtuel sur le thread matériel associé à une ressource d'exécution existante.|  
|[ISchedulerProxy::RequestInitialVirtualProcessors, méthode](../Topic/ISchedulerProxy::RequestInitialVirtualProcessors%20Method.md)|Demande une allocation initiale de racines de processeur virtuel.  Chaque racine de processeur virtuel représente la capacité à exécuter un thread qui peut exécuter un travail pour le planificateur.|  
|[ISchedulerProxy::Shutdown, méthode](../Topic/ISchedulerProxy::Shutdown%20Method.md)|Notifie le Gestionnaire de ressources que le planificateur est en cours de fermeture.  Le Gestionnaire des ressources récupérera alors immédiatement toutes les ressources accordées au planificateur.|  
|[ISchedulerProxy::SubscribeCurrentThread, méthode](../Topic/ISchedulerProxy::SubscribeCurrentThread%20Method.md)|Inscrit le thread actuel auprès du Gestionnaire de ressources, en l'associant à ce planificateur.|  
|[ISchedulerProxy::UnbindContext, méthode](../Topic/ISchedulerProxy::UnbindContext%20Method.md)|Dissocie un proxy de thread du contexte d'exécution spécifié par le paramètre `pContext` et le retourne au pool libre de la fabrique de proxys de thread.  Cette méthode peut être appelée uniquement dans un contexte d'exécution qui a été lié via la méthode [ISchedulerProxy::BindContext](../Topic/ISchedulerProxy::BindContext%20Method.md) et n'a pas encore été démarré en étant le paramètre `pContext` d'un appel de méthode [d'IThreadProxy::SwitchTo](../Topic/IThreadProxy::SwitchTo%20Method.md).|  
  
## Notes  
 Le Gestionnaire des ressources donne une interface `ISchedulerProxy` à chaque planificateur qui s'enregistre auprès d'elle à l'aide de la méthode [IResourceManager::RegisterScheduler](../Topic/IResourceManager::RegisterScheduler%20Method.md).  
  
## Hiérarchie d'héritage  
 `ISchedulerProxy`  
  
## Configuration requise  
 **En\-tête :** concrtrm.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IScheduler, structure](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [IThreadProxy, structure](../../../parallel/concrt/reference/ithreadproxy-structure.md)   
 [IVirtualProcessorRoot, structure](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)   
 [IResourceManager, structure](../../../parallel/concrt/reference/iresourcemanager-structure.md)