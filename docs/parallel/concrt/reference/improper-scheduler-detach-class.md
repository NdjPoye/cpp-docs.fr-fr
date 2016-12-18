---
title: "improper_scheduler_detach, classe | Microsoft Docs"
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
  - "concrt/concurrency::improper_scheduler_detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_scheduler_detach (classe)"
ms.assetid: 30132102-c900-4951-a470-b63b4e3aa2d2
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# improper_scheduler_detach, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée lorsque la méthode d' `CurrentScheduler::Detach` est appelée sur un contexte n'a été attaché à aucun planificateur à l'aide de la méthode d' `Attach` d'objet d' `Scheduler` .  
  
## Syntaxe  
  
```  
class improper_scheduler_detach : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[improper\_scheduler\_detach::improper\_scheduler\_detach, constructeur](../Topic/improper_scheduler_detach::improper_scheduler_detach%20Constructor.md)|Surchargé.  Construit un objet `improper_scheduler_detach`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `improper_scheduler_detach`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler, classe](../../../parallel/concrt/reference/scheduler-class.md)   
 [CurrentScheduler::Detach, méthode](../Topic/CurrentScheduler::Detach%20Method.md)   
 [Scheduler::Attach, méthode](../Topic/Scheduler::Attach%20Method.md)