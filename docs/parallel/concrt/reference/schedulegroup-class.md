---
title: "ScheduleGroup, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::ScheduleGroup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ScheduleGroup (classe)"
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# ScheduleGroup, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Représente une abstraction pour un groupe de planification.  Les groupes de planification organisent un ensemble de travaux connexes qui bénéficient d'être planifiés près des uns des autres, au niveau temporel en exécutant une autre tâche du même groupe avant de se déplacer vers un autre groupe, ou au niveau spatial en exécutant plusieurs éléments du même groupe sur le même nœud NUMA ou socket physique.  
  
## Syntaxe  
  
```  
class ScheduleGroup;  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[ScheduleGroup::~ScheduleGroup, destructeur](../Topic/ScheduleGroup::~ScheduleGroup%20Destructor.md)||  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ScheduleGroup::Id, méthode](../Topic/ScheduleGroup::Id%20Method.md)|Retourne un identificateur pour le groupe de planification qui est unique dans le planificateur auquel le groupe appartient.|  
|[ScheduleGroup::Reference, méthode](../Topic/ScheduleGroup::Reference%20Method.md)|Incrémente le nombre de références du groupe de planification.|  
|[ScheduleGroup::Release, méthode](../Topic/ScheduleGroup::Release%20Method.md)|Décrémente le nombre de références du groupe de planification.|  
|[ScheduleGroup::ScheduleTask, méthode](../Topic/ScheduleGroup::ScheduleTask%20Method.md)|Planifie une tâche légère dans le groupe de planification.|  
  
## Hiérarchie d'héritage  
 `ScheduleGroup`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [CurrentScheduler, classe](../../../parallel/concrt/reference/currentscheduler-class.md)   
 [Scheduler, classe](../../../parallel/concrt/reference/scheduler-class.md)   
 [Planificateur de tâches](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)