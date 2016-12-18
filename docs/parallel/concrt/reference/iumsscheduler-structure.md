---
title: "IUMSScheduler, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IUMSScheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSScheduler (structure)"
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
caps.latest.revision: 18
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IUMSScheduler, structure
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Interface à une abstraction d'un planificateur de travail qui veut que le Gestionnaire de ressources du runtime d'accès concurrentiel lui envoie des threads UMS \(user mode schedulable\).  Le Gestionnaire des ressources utilise cette interface pour communiquer avec les planificateurs de thread UMS.  L'interface `IUMSScheduler` hérite de l'interface `IScheduler`.  
  
## Syntaxe  
  
```  
struct IUMSScheduler : public IScheduler;  
```  
  
## Membres  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IUMSScheduler::SetCompletionList, méthode](../Topic/IUMSScheduler::SetCompletionList%20Method.md)|Assigne une interface `IUMSCompletionList` à un planificateur de thread UMS.|  
  
## Notes  
 Si vous implémentez un planificateur personnalisé qui communique avec le Gestionnaire de ressources et souhaitez que les threads UMS soient transmis à votre planificateur au lieu de threads Win32 ordinaires, vous devez fournir une implémentation de l'interface `IUMSScheduler`.  De plus, vous devez affecter à la stratégie de la clé de stratégie du planificateur `SchedulerKind` la valeur `UmsThreadDefault`.  Si la stratégie spécifie le thread UMS, l'interface `IScheduler` passée comme un paramètre à la méthode [IResourceManager::RegisterScheduler](../Topic/IResourceManager::RegisterScheduler%20Method.md) doit être une interface `IUMSScheduler`.  
  
 Le Gestionnaire des ressources est en mesure de vous donner des threads UMS uniquement sur les systèmes d'exploitation dotés de la fonctionnalité UMS. Systèmes d'exploitation 64 bits avec la version Windows 7 et des threads UMS de prise en charge plus élevée.  Si vous créez une stratégie du planificateur avec la clé `SchedulerKind` avec la valeur `UmsThreadDefault` et que la plateforme sous\-jacente ne prend pas en charge UMS, la valeur de la clé `SchedulerKind` de cette stratégie sera modifiée en `ThreadScheduler`.  Vous devez toujours relire cette valeur de stratégie avant de pouvoir vous attendre à recevoir des threads UMS.  
  
 L'interface `IUMSScheduler` est une extrémité d'un canal bidirectionnel de communication entre un planificateur et le Gestionnaire des ressources.  L'autre extrémité est représentée par les interfaces `IResourceManager` et `ISchedulerProxy` implémentées par le Gestionnaire des ressources.  
  
## Hiérarchie d'héritage  
 [IScheduler](../../../parallel/concrt/reference/ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## Configuration requise  
 **En\-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [PolicyElementKey, énumération](../Topic/PolicyElementKey%20Enumeration.md)   
 [IScheduler, structure](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [IUMSCompletionList, structure](../../../parallel/concrt/reference/iumscompletionlist-structure.md)   
 [IResourceManager, structure](../../../parallel/concrt/reference/iresourcemanager-structure.md)