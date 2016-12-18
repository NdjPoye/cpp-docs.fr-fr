---
title: "scheduler_ptr::Structure (runtime d&#39;acc&#232;s concurrentiel) | Microsoft Docs"
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
  - "pplinterface/concurrency::scheduler_ptr"
dev_langs: 
  - "C++"
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
caps.latest.revision: 8
caps.handback.revision: 1
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# scheduler_ptr::Structure (runtime d&#39;acc&#232;s concurrentiel)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Représente un pointeur vers un planificateur.  Cette classe existe pour permettre la spécification d'une durée de vie partagée à l'aide de shared\_ptr ou d'une référence simple à l'aide d'un pointeur brut.  
  
## Syntaxe  
  
```  
struct scheduler_ptr;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[scheduler\_ptr::scheduler\_ptr, constructeur \(runtime d'accès concurrentiel\)](../Topic/scheduler_ptr::scheduler_ptr%20Constructor%20\(Concurrency%20Runtime\).md)|Surchargé.  Crée un pointeur de planificateur de shared\_ptr vers le planificateur|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[scheduler\_ptr::get, méthode \(runtime d'accès concurrentiel\)](../Topic/scheduler_ptr::get%20Method%20\(Concurrency%20Runtime\).md)|Retourne le pointeur brut au planificateur|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[scheduler\_ptr::operator, opérateur booléen \(runtime d'accès concurrentiel\)](../Topic/scheduler_ptr::operator%20bool%20Operator%20\(Concurrency%20Runtime\).md)|Teste si le pointeur du planificateur a une valeur non null|  
|[scheduler\_ptr::operator\-\>, opérateur \(runtime d'accès concurrentiel\)](../Topic/scheduler_ptr::operator-%3E%20Operator%20\(Concurrency%20Runtime\).md)|Se comporte comme un pointeur|  
  
## Hiérarchie d'héritage  
 `scheduler_ptr`  
  
## Configuration requise  
 **En\-tête :** pplinterface.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)