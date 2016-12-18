---
title: "invalid_scheduler_policy_key, classe | Microsoft Docs"
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
  - "concrt/concurrency::invalid_scheduler_policy_key"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_scheduler_policy_key (classe)"
ms.assetid: 6a7c42fe-9bc4-4a02-bebb-99fe9ef9817d
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# invalid_scheduler_policy_key, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée lorsqu'une clé valide ou inconnue est passée à un constructeur d'objet d' `SchedulerPolicy` , ou la méthode d' `SetPolicyValue` d'objet d' `SchedulerPolicy` est passée une clé qui doit être modifiée à l'aide de autres moyens tels que la méthode d' `SetConcurrencyLimits` .  
  
## Syntaxe  
  
```  
class invalid_scheduler_policy_key : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[invalid\_scheduler\_policy\_key::invalid\_scheduler\_policy\_key, constructeur](../Topic/invalid_scheduler_policy_key::invalid_scheduler_policy_key%20Constructor.md)|Surchargé.  Construit un objet `invalid_scheduler_policy_key`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `invalid_scheduler_policy_key`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [SchedulerPolicy, classe](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [PolicyElementKey, énumération](../Topic/PolicyElementKey%20Enumeration.md)   
 [SchedulerPolicy::SetPolicyValue, méthode](../Topic/SchedulerPolicy::SetPolicyValue%20Method.md)   
 [SchedulerPolicy::SetConcurrencyLimits, méthode](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)