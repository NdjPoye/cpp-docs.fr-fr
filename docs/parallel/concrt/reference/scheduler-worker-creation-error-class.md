---
title: "scheduler_worker_creation_error, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::scheduler_worker_creation_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scheduler_worker_creation_error (classe)"
ms.assetid: 4aec1c3e-c32a-41b2-899d-2d898f23b3c7
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# scheduler_worker_creation_error, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée en raison d'un échec dans la création d'un contexte d'exécution de worker du runtime d'accès concurrentiel.  
  
## Syntaxe  
  
```  
class scheduler_worker_creation_error : public scheduler_resource_allocation_error;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[scheduler\_worker\_creation\_error::scheduler\_worker\_creation\_error, constructeur](../Topic/scheduler_worker_creation_error::scheduler_worker_creation_error%20Constructor.md)|Surchargé.  Construit un objet `scheduler_worker_creation_error`.|  
  
## Notes  
 Cette exception est généralement levée lorsqu'un appel au système d'exploitation pour créer des contextes d'exécution à partir du runtime d'accès concurrentiel échoue.  Les contextes d'exécution sont des threads qui exécutent des tâches dans le runtime d'accès concurrentiel.  Le code d'erreur qui devrait normalement être retourné par un appel à la méthode Win32 `GetLastError` est converti en une valeur de type `HRESULT` et peut être extrait en utilisant la méthode de type de classe `get_error_code`.  
  
## Hiérarchie d'héritage  
 `exception`  
  
 [scheduler\_resource\_allocation\_error](../../../parallel/concrt/reference/scheduler-resource-allocation-error-class.md)  
  
 `scheduler_worker_creation_error`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)