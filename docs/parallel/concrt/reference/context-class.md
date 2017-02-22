---
title: "Context, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::Context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Context (classe)"
ms.assetid: c0d553f3-961d-4ecd-9a29-4fa4351673b8
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# Context, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Représente une abstraction pour un contexte d'exécution.  
  
## Syntaxe  
  
```  
class Context;  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[Context::~Context, destructeur](../Topic/Context::~Context%20Destructor.md)||  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[Context::Block, méthode](../Topic/Context::Block%20Method.md)|Bloque le contexte actuel.|  
|[Context::CurrentContext, méthode](../Topic/Context::CurrentContext%20Method.md)|Retourne un pointeur au contexte actuel.|  
|[Context::GetId, méthode](../Topic/Context::GetId%20Method.md)|Retourne un identificateur pour le contexte qui est unique dans le planificateur auquel le contexte appartient.|  
|[Context::GetScheduleGroupId, méthode](../Topic/Context::GetScheduleGroupId%20Method.md)|Retourne un identificateur pour le groupe de planification sur lequel le contexte fonctionne actuellement.|  
|[Context::GetVirtualProcessorId, méthode](../Topic/Context::GetVirtualProcessorId%20Method.md)|Retourne un identificateur pour le processeur virtuel sur lequel le contexte s'exécute actuellement.|  
|[Context::Id, méthode](../Topic/Context::Id%20Method.md)|Retourne un identificateur pour le contexte actuel qui est unique dans le planificateur auquel le contexte actuel appartient.|  
|[Context::IsCurrentTaskCollectionCanceling, méthode](../Topic/Context::IsCurrentTaskCollectionCanceling%20Method.md)|Retourne une indication spécifiant si la collection de tâches qui s'exécute actuellement inline sur le contexte actuel est en cours d'annulation \(ou le sera bientôt\).|  
|[Context::IsSynchronouslyBlocked, méthode](../Topic/Context::IsSynchronouslyBlocked%20Method.md)|Détermine si le contexte est bloqué de façon synchrone.  Un contexte est considéré pour être bloqué de façon synchrone s'il a exécuté explicitement une action qui a mené au blocage.|  
|[Context::Oversubscribe, méthode](../Topic/Context::Oversubscribe%20Method.md)|Injecte un processeur virtuel supplémentaire dans un planificateur pour la durée d'un bloc de code en cas d'appel sur un contexte s'exécutant sur l'un des processeurs virtuels dans ce planificateur.|  
|[Context::ScheduleGroupId, méthode](../Topic/Context::ScheduleGroupId%20Method.md)|Retourne un identificateur pour le groupe de planification sur lequel le contexte actuel fonctionne.|  
|[Context::Unblock, méthode](../Topic/Context::Unblock%20Method.md)|Débloque le contexte et le rend exécutable.|  
|[Context::VirtualProcessorId, méthode](../Topic/Context::VirtualProcessorId%20Method.md)|Retourne un identificateur pour le processeur virtuel sur lequel le contexte actuel s'exécute.|  
|[Context::Yield, méthode](../Topic/Context::Yield%20Method.md)|Cède l'exécution afin qu'un autre contexte puisse s'exécuter.  Si aucun autre contexte n'est disponible pour prendre le relais, le planificateur peut passer à un processus d'un autre système d'exploitation.|  
  
## Notes  
 Le planificateur de runtime d'accès concurrentiel \(voir [Planificateur](../../../parallel/concrt/reference/scheduler-class.md)\) utilise des contextes d'exécution pour exécuter le travail mis en file d'attente par votre application sur le planificateur.  Un processus Win32 est un exemple de contexte d'exécution sur un système d'exploitation Windows.  
  
 À tout moment, le niveau d'accès concurrentiel d'un planificateur est égal au nombre de processeurs virtuels qui lui sont accordés par le Gestionnaire des ressources.  Un processeur virtuel est une représentation abstraite d'une ressource de traitement qui mappe à un thread matériel dans le système sous\-jacent.  Seul un contexte de planificateur unique peut s'exécuter sur un processeur virtuel à un moment donné.  
  
 Le planificateur est coopératif par nature et un contexte en cours d'exécution peut céder son processeur virtuel à un contexte différent à tout moment s'il souhaite entrer dans un état d'attente.  À l'issue de l'attente, il ne peut pas reprendre tant qu'un processeur virtuel disponible dans le planificateur commence à l'exécuter.  
  
## Hiérarchie d'héritage  
 `Context`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler, classe](../../../parallel/concrt/reference/scheduler-class.md)   
 [Planificateur de tâches](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)