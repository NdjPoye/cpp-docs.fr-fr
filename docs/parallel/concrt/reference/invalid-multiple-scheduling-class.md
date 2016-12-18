---
title: "invalid_multiple_scheduling, classe | Microsoft Docs"
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
  - "concrt/concurrency::invalid_multiple_scheduling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_multiple_scheduling (classe)"
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# invalid_multiple_scheduling, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée lorsqu'un objet d' `task_handle` est planifié plusieurs fois à l'aide de la méthode d' `run` d'objet d' `task_group` ou d' `structured_task_group` sans appel intermédiaire aux méthodes d' `wait` ou d' `run_and_wait` .  
  
## Syntaxe  
  
```  
class invalid_multiple_scheduling : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[invalid\_multiple\_scheduling::invalid\_multiple\_scheduling, constructeur](../Topic/invalid_multiple_scheduling::invalid_multiple_scheduling%20Constructor.md)|Surchargé.  Construit un objet `invalid_multiple_scheduling`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `invalid_multiple_scheduling`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_handle, classe](../../../parallel/concrt/reference/task-handle-class.md)   
 [task\_group, classe](../Topic/task_group%20Class.md)   
 [task\_group::run, méthode](../Topic/task_group::run%20Method.md)   
 [task\_group::wait, méthode](../Topic/task_group::wait%20Method.md)   
 [task\_group::run\_and\_wait, méthode](../Topic/task_group::run_and_wait%20Method.md)   
 [structured\_task\_group, classe](../../../parallel/concrt/reference/structured-task-group-class.md)   
 [structured\_task\_group::run, méthode](../Topic/structured_task_group::run%20Method.md)   
 [structured\_task\_group::wait, méthode](../Topic/structured_task_group::wait%20Method.md)   
 [structured\_task\_group::run\_and\_wait, méthode](../Topic/structured_task_group::run_and_wait%20Method.md)