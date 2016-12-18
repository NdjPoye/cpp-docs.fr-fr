---
title: "IThreadProxy, structure | Microsoft Docs"
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
  - "concrtrm/concurrency::IThreadProxy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IThreadProxy (structure)"
ms.assetid: feb89241-a555-4e61-ad48-40add54daeca
caps.latest.revision: 21
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IThreadProxy, structure
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Abstraction d'un thread d'exécution.  Selon la clé de stratégie `SchedulerType` du planificateur que vous créez, le Gestionnaire des ressources vous accordera un proxy de thread stocké par un thread Win32 standard ou un thread UMS \(User\-Mode Schedulable\).  Les threads UMS sont pris en charge sur les systèmes d'exploitation 64 bits avec la version Windows 7 et supérieure.  
  
## Syntaxe  
  
```  
struct IThreadProxy;  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IThreadProxy::GetId, méthode](../Topic/IThreadProxy::GetId%20Method.md)|Retourne un identificateur unique pour le proxy de thread.|  
|[IThreadProxy::SwitchOut, méthode](../Topic/IThreadProxy::SwitchOut%20Method.md)|Dissocie le contexte de la racine de processeur virtuel sous\-jacente.|  
|[IThreadProxy::SwitchTo, méthode](../Topic/IThreadProxy::SwitchTo%20Method.md)|Exécute un changement de contexte coopératif du contexte en cours d'exécution.|  
|[IThreadProxy::YieldToSystem, méthode](../Topic/IThreadProxy::YieldToSystem%20Method.md)|Oblige le thread appelant à céder l'exécution à un autre thread prêt à s'exécuter sur le processeur actuel.  Le système d'exploitation sélectionne le thread suivant à exécuter.|  
  
## Notes  
 Les proxys de thread sont associés aux contextes d'exécution représentés par l'interface `IExecutionContext` comme un moyen de distribuer le travail.  
  
## Hiérarchie d'héritage  
 `IThreadProxy`  
  
## Configuration requise  
 **En\-tête :** concrtrm.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IExecutionContext, structure](../../../parallel/concrt/reference/iexecutioncontext-structure.md)   
 [IScheduler, structure](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [IVirtualProcessorRoot, structure](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)