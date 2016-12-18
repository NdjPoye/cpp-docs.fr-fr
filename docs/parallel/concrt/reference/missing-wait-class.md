---
title: "missing_wait, classe | Microsoft Docs"
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
  - "concrt/concurrency::missing_wait"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "missing_wait (classe)"
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# missing_wait, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée lorsqu'il existe des tâches planifiées toujours à un objet d' `task_group` ou d' `structured_task_group` tandis que le destructeur de l'objet exécute.  Cette exception ne sera jamais levée si le destructeur est atteint en raison d'un déroulement de pile suite à une exception.  
  
## Syntaxe  
  
```  
class missing_wait : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[missing\_wait::missing\_wait, constructeur](../Topic/missing_wait::missing_wait%20Constructor.md)|Surchargé.  Construit un objet `missing_wait`.|  
  
## Notes  
 En l'absence de flux d'exception, vous êtes chargé de l'appel de la méthode `wait` ou `run_and_wait` d'un objet `task_group` ou `structured_task_group` avant d'autoriser la destruction de cet objet.  Le runtime lève cette exception pour indiquer que vous avez oublié d'appeler la méthode `wait` ou `run_and_wait`.  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `missing_wait`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_group, classe](../Topic/task_group%20Class.md)   
 [task\_group::wait, méthode](../Topic/task_group::wait%20Method.md)   
 [task\_group::run\_and\_wait, méthode](../Topic/task_group::run_and_wait%20Method.md)   
 [structured\_task\_group, classe](../../../parallel/concrt/reference/structured-task-group-class.md)   
 [structured\_task\_group::wait, méthode](../Topic/structured_task_group::wait%20Method.md)   
 [structured\_task\_group::run\_and\_wait, méthode](../Topic/structured_task_group::run_and_wait%20Method.md)