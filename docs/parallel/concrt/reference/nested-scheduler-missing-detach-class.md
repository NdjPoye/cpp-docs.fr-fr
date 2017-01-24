---
title: "nested_scheduler_missing_detach, classe | Microsoft Docs"
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
  - "concrt/concurrency::nested_scheduler_missing_detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nested_scheduler_missing_detach (classe)"
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# nested_scheduler_missing_detach, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception qui est renvoyée lorsque le runtime d'accès concurrentiel détecte que l'on a omis d'appeler la méthode `CurrentScheduler::Detach` sur un contexte joint à un deuxième planificateur via la méthode `Attach` de l'objet `Scheduler`.  
  
## Syntaxe  
  
```  
class nested_scheduler_missing_detach : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[nested\_scheduler\_missing\_detach::nested\_scheduler\_missing\_detach, constructeur](../Topic/nested_scheduler_missing_detach::nested_scheduler_missing_detach%20Constructor.md)|Surchargé.  Construit un objet `nested_scheduler_missing_detach`.|  
  
## Notes  
 Cette exception est levée uniquement lorsque vous imbriquez un planificateur à l'intérieur d'un autre en appelant la méthode `Attach` d'un objet `Scheduler` dans un contexte appartenant ou attaché à un autre planificateur.  Le runtime d'accès concurrentiel lève cette exception de façon opportuniste lorsqu'il peut détecter le scénario comme une aide pour localiser le problème.  Toutes les instances négligeant l'appel à la méthode `CurrentScheduler::Detach` ne lèvent pas cette exception.  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `nested_scheduler_missing_detach`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler, classe](../../../parallel/concrt/reference/scheduler-class.md)   
 [CurrentScheduler::Detach, méthode](../Topic/CurrentScheduler::Detach%20Method.md)   
 [Scheduler::Attach, méthode](../Topic/Scheduler::Attach%20Method.md)