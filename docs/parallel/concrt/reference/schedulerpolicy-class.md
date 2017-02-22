---
title: "SchedulerPolicy, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::SchedulerPolicy"
  - "concrtrm/concurrency::SchedulerPolicy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SchedulerPolicy (classe)"
ms.assetid: bcebf51a-65f8-45a3-809b-d1ff93527dc4
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# SchedulerPolicy, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `SchedulerPolicy` contient un jeu de paires clé\/valeur, un pour chaque élément de stratégie, qui contrôle le comportement d'une instance du planificateur.  
  
## Syntaxe  
  
```  
class SchedulerPolicy;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[SchedulerPolicy::SchedulerPolicy, constructeur](../Topic/SchedulerPolicy::SchedulerPolicy%20Constructor.md)|Surchargé.  Construit une nouvelle stratégie du planificateur et la remplit avec les valeurs des [clés de stratégie](../Topic/PolicyElementKey%20Enumeration.md) prises en charge par les planificateurs de runtime d'accès concurrentiel et le Gestionnaire des ressources.|  
|[SchedulerPolicy::~SchedulerPolicy, destructeur](../Topic/SchedulerPolicy::~SchedulerPolicy%20Destructor.md)|Détruit une stratégie de planificateur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[SchedulerPolicy::GetPolicyValue, méthode](../Topic/SchedulerPolicy::GetPolicyValue%20Method.md)|Récupère la valeur de la clé de stratégie fournie comme paramètre `_Key`.|  
|[SchedulerPolicy::SetConcurrencyLimits, méthode](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)|Définit en même temps les stratégies `MinConcurrency` et `MaxConcurrency` sur l'objet `SchedulerPolicy`.|  
|[SchedulerPolicy::SetPolicyValue, méthode](../Topic/SchedulerPolicy::SetPolicyValue%20Method.md)|Définit la valeur de la clé de stratégie fournie comme paramètre `_Key` et retourne l'ancienne valeur.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[SchedulerPolicy::operator\=, opérateur](../Topic/SchedulerPolicy::operator=%20Operator.md)|Assigne la stratégie du planificateur à partir d'une autre stratégie de planificateur.|  
  
## Notes  
 Pour plus d'informations sur les stratégies qui peuvent être contrôlées en utilisant la classe `SchedulerPolicy`, consultez [PolicyElementKey, énumération](../Topic/PolicyElementKey%20Enumeration.md).  
  
## Hiérarchie d'héritage  
 `SchedulerPolicy`  
  
## Configuration requise  
 **En\-tête :** concrt.h, concrtrm.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [PolicyElementKey, énumération](../Topic/PolicyElementKey%20Enumeration.md)   
 [CurrentScheduler, classe](../../../parallel/concrt/reference/currentscheduler-class.md)   
 [Scheduler, classe](../../../parallel/concrt/reference/scheduler-class.md)   
 [Planificateur de tâches](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)