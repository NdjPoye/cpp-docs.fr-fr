---
title: "improper_scheduler_attach, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::improper_scheduler_attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_scheduler_attach (classe)"
ms.assetid: 5a76da0a-091b-4748-8f62-b3a28f674f9e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# improper_scheduler_attach, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée lorsque la méthode d' `Attach` est appelée sur un objet d' `Scheduler` qui est déjà attache au contexte actuel.  
  
## Syntaxe  
  
```  
class improper_scheduler_attach : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[improper\_scheduler\_attach::improper\_scheduler\_attach, constructeur](../Topic/improper_scheduler_attach::improper_scheduler_attach%20Constructor.md)|Surchargé.  Construit un objet `improper_scheduler_attach`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `improper_scheduler_attach`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler, classe](../../../parallel/concrt/reference/scheduler-class.md)   
 [Scheduler::Attach, méthode](../Topic/Scheduler::Attach%20Method.md)