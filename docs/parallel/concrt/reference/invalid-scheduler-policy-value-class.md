---
title: "invalid_scheduler_policy_value, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::invalid_scheduler_policy_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_scheduler_policy_value (classe)"
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# invalid_scheduler_policy_value, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée lorsqu'une clé de stratégie d'un objet d' `SchedulerPolicy` a une valeur valide pour cette clé.  
  
## Syntaxe  
  
```  
class invalid_scheduler_policy_value : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[invalid\_scheduler\_policy\_value::invalid\_scheduler\_policy\_value, constructeur](../Topic/invalid_scheduler_policy_value::invalid_scheduler_policy_value%20Constructor.md)|Surchargé.  Construit un objet `invalid_scheduler_policy_value`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `invalid_scheduler_policy_value`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [SchedulerPolicy, classe](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [PolicyElementKey, énumération](../Topic/PolicyElementKey%20Enumeration.md)   
 [SchedulerPolicy::SetPolicyValue, méthode](../Topic/SchedulerPolicy::SetPolicyValue%20Method.md)   
 [SchedulerPolicy::SetConcurrencyLimits, méthode](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)