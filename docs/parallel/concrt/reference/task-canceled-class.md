---
title: "task_canceled, classe | Microsoft Docs"
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
  - "concrt/concurrency::task_canceled"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_canceled (classe)"
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
caps.latest.revision: 11
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# task_canceled, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée par la couche de tâches PPL afin de forcer la tâche en cours pour annuler.  Il est également levée par la `get()` méthode sur  [tâche](../Topic/Task%20Class%20-%20Internal%20Members.md), pour une tâche annulée.  
  
## Syntaxe  
  
```  
class task_canceled : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[task\_canceled::task\_canceled, constructeur](../Topic/task_canceled::task_canceled%20Constructor.md)|Surchargé.  Construit un objet `task_canceled`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `task_canceled`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 **Espace de noms :**  accès concurrentiel  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task::get, méthode](../Topic/task::get%20Method.md)   
 [cancel\_current\_task, fonction](../Topic/cancel_current_task%20Function.md)