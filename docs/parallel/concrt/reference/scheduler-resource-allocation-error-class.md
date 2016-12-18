---
title: "scheduler_resource_allocation_error, classe | Microsoft Docs"
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
  - "concrt/concurrency::scheduler_resource_allocation_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scheduler_resource_allocation_error (classe)"
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# scheduler_resource_allocation_error, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception qui est renvoyée en raison de l'échec de l'acquisition d'une ressource critique dans le runtime d'accès concurrentiel.  
  
## Syntaxe  
  
```  
class scheduler_resource_allocation_error : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[scheduler\_resource\_allocation\_error::scheduler\_resource\_allocation\_error, constructeur](../Topic/scheduler_resource_allocation_error::scheduler_resource_allocation_error%20Constructor.md)|Surchargé.  Construit un objet `scheduler_resource_allocation_error`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[scheduler\_resource\_allocation\_error::get\_error\_code, méthode](../Topic/scheduler_resource_allocation_error::get_error_code%20Method.md)|Retourne le code d'erreur qui a provoqué l'exception.|  
  
## Notes  
 Cette exception est généralement levée lorsqu'un appel au système d'exploitation à partir du runtime d'accès concurrentiel échoue.  Le code d'erreur qui devrait normalement être retourné par un appel à la méthode Win32 `GetLastError` est converti en une valeur de type `HRESULT` et peut être extrait en utilisant la méthode `get_error_code`.  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `scheduler_resource_allocation_error`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)