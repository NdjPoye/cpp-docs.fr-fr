---
title: "improper_scheduler_reference, classe | Microsoft Docs"
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
  - "concrt/concurrency::improper_scheduler_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_scheduler_reference (classe)"
ms.assetid: 434a7512-7796-4255-92a7-f3bf71c6a7a7
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# improper_scheduler_reference, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée lorsque la méthode d' `Reference` est appelée sur un objet d' `Scheduler` qui s'arrête, d'un contexte qui ne fait pas partie de ce planificateur.  
  
## Syntaxe  
  
```  
class improper_scheduler_reference : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[improper\_scheduler\_reference::improper\_scheduler\_reference, constructeur](../Topic/improper_scheduler_reference::improper_scheduler_reference%20Constructor.md)|Surchargé.  Construit un objet `improper_scheduler_reference`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `improper_scheduler_reference`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler, classe](../../../parallel/concrt/reference/scheduler-class.md)   
 [Scheduler::Reference, méthode](../Topic/Scheduler::Reference%20Method.md)