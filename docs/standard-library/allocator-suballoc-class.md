---
title: "allocator_suballoc, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators::allocator_suballoc"
  - "allocator_suballoc"
  - "stdext.allocators.allocator_suballoc"
  - "allocators/stdext::allocators::allocator_suballoc"
  - "stdext::allocators::allocator_suballoc"
  - "allocators/stdext::allocator_suballoc"
  - "allocators.allocator_suballoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_suballoc (classe)"
ms.assetid: 50c6a5c0-d00d-4276-9285-d908fd4f6483
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# allocator_suballoc, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui gère l’allocation de stockage et la libération des objets de type `Type` à l’aide d’un cache de type [cache\_suballoc](../standard-library/cache-suballoc-class.md).  
  
## Syntaxe  
  
```  
template <class Type>  
    class allocator_suballoc;  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Type`|Type des éléments alloués par l'allocateur.|  
  
## Notes  
 Le [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) macro transmet cette classe comme le `name` paramètre dans l’instruction suivante : `ALLOCATOR_DECL(CACHE_SUBALLOC, SYNC_DEFAULT, allocator_suballoc);`  
  
## Configuration requise  
 **En\-tête :** \<allocators\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<allocators\>](../standard-library/allocators-header.md)