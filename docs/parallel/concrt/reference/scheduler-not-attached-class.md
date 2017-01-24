---
title: "scheduler_not_attached, classe | Microsoft Docs"
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
  - "concrt/concurrency::scheduler_not_attached"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scheduler_not_attached (classe)"
ms.assetid: 26001970-b400-463b-be3d-8623359c399a
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# scheduler_not_attached, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée lorsque l'effectue une opération qui requiert un planificateur à associer au contexte actuel et il n'est pas.  
  
## Syntaxe  
  
```  
class scheduler_not_attached : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[scheduler\_not\_attached::scheduler\_not\_attached, constructeur](../Topic/scheduler_not_attached::scheduler_not_attached%20Constructor.md)|Surchargé.  Construit un objet `scheduler_not_attached`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `scheduler_not_attached`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler, classe](../../../parallel/concrt/reference/scheduler-class.md)   
 [Scheduler::Attach, méthode](../Topic/Scheduler::Attach%20Method.md)