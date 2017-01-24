---
title: "allocator_variable_size, classe | Microsoft Docs"
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
  - "allocators.allocator_variable_size"
  - "allocators::allocator_variable_size"
  - "allocators/stdext::allocator_variable_size"
  - "stdext.allocators.allocator_variable_size"
  - "allocator_variable_size"
  - "allocators/stdext::allocators::allocator_variable_size"
  - "stdext::allocators::allocator_variable_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_variable_size (classe)"
ms.assetid: c3aa4105-ae45-4385-bbbe-9f23060478cb
caps.latest.revision: 16
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# allocator_variable_size, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui gère l'allocation de stockage et récupérer des objets de type `Type` à un cache de type [cache\_freelist](../standard-library/cache-freelist-class.md) avec une longueur gérée par [max\_variable\_size](../standard-library/max-variable-size-class.md).  
  
## Syntaxe  
  
```  
template <class Type>  
    class allocator_variable_size;  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Type`|Le type d'éléments alloués par l'allocateur.|  
  
## Notes  
 La macro d'[ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) passe cette classe en tant que paramètre d'`name` dans l'instruction suivante : `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_variable_size), SYNC_DEFAULT, allocator_variable_size);`  
  
## Configuration requise  
 **En\-tête :**allocateurs \<de \>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<allocators\>](../standard-library/allocators-header.md)