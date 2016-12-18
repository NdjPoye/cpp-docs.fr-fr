---
title: "invalid_scheduler_policy_thread_specification, classe | Microsoft Docs"
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
  - "concrt/concurrency::invalid_scheduler_policy_thread_specification"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_scheduler_policy_thread_specification (classe)"
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# invalid_scheduler_policy_thread_specification, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée lorsqu'une tentative est faite pour définir les limites d'accès concurrentiel d'un objet d' `SchedulerPolicy` ce que la valeur de la clé d' `MinConcurrency` est inférieure à la valeur de la clé d' `MaxConcurrency` .  
  
## Syntaxe  
  
```  
class invalid_scheduler_policy_thread_specification : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[invalid\_scheduler\_policy\_thread\_specification::invalid\_scheduler\_policy\_thread\_specification, constructeur](../Topic/invalid_scheduler_policy_thread_specification::invalid_scheduler_policy_thread_specification%20Constructor.md)|Surchargé.  Construit un objet `invalid_scheduler_policy_value`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `invalid_scheduler_policy_thread_specification`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [SchedulerPolicy, classe](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [PolicyElementKey, énumération](../Topic/PolicyElementKey%20Enumeration.md)   
 [SchedulerPolicy::SetConcurrencyLimits, méthode](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)