---
title: "IExecutionContext, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IExecutionContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IExecutionContext (structure)"
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# IExecutionContext, structure
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Interface à un contexte d'exécution qui peut s'exécuter sur un processeur virtuel donné et dont le contexte peut être modifié de manière coopérative.  
  
## Syntaxe  
  
```  
struct IExecutionContext;  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IExecutionContext::Dispatch, méthode](../Topic/IExecutionContext::Dispatch%20Method.md)|La méthode appelée lorsqu'un proxy de thread commence à exécuter un contexte d'exécution particulier.  Cela doit être la routine de travail principale pour votre planificateur.|  
|[IExecutionContext::GetId, méthode](../Topic/IExecutionContext::GetId%20Method.md)|Retourne un identificateur unique pour le contexte d'exécution.|  
|[IExecutionContext::GetProxy, méthode](../Topic/IExecutionContext::GetProxy%20Method.md)|Retourne une interface au proxy de thread qui exécute ce contexte.|  
|[IExecutionContext::GetScheduler, méthode](../Topic/IExecutionContext::GetScheduler%20Method.md)|Retourne une interface au planificateur auquel ce contexte d'exécution appartient.|  
|[IExecutionContext::SetProxy, méthode](../Topic/IExecutionContext::SetProxy%20Method.md)|Associe un proxy de thread à ce contexte d'exécution.  Le proxy de thread associé appelle cette méthode juste avant qu'il ne commence à exécuter la méthode `Dispatch` du contexte.|  
  
## Notes  
 Si vous implémentez un planificateur personnalisé qui interagit avec le Gestionnaire de ressources du runtime d'accès concurrentiel, vous devrez implémenter l'interface `IExecutionContext`.  Les threads créés par le Gestionnaire des ressources exécutent le travail au nom de votre planificateur en exécutant la méthode `IExecutionContext::Dispatch`.  
  
## Hiérarchie d'héritage  
 `IExecutionContext`  
  
## Configuration requise  
 **En\-tête :** concrtrm.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IScheduler, structure](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [IThreadProxy, structure](../../../parallel/concrt/reference/ithreadproxy-structure.md)