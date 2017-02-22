---
title: "default_scheduler_exists, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::default_scheduler_exists"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "default_scheduler_exists (classe)"
ms.assetid: f6e575e2-4e0f-455a-9e06-54f462ce0c1c
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# default_scheduler_exists, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée lorsque la méthode d' `Scheduler::SetDefaultSchedulerPolicy` est appelée lorsqu'un planificateur par défaut existe déjà dans le processus.  
  
## Syntaxe  
  
```  
class default_scheduler_exists : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[default\_scheduler\_exists::default\_scheduler\_exists, constructeur](../Topic/default_scheduler_exists::default_scheduler_exists%20Constructor.md)|Surchargé.  Construit un objet `default_scheduler_exists`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `default_scheduler_exists`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler::SetDefaultSchedulerPolicy, méthode](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md)