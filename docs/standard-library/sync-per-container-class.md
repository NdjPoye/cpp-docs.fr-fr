---
title: "sync_per_container, classe | Microsoft Docs"
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
  - "stdext.sync_per_container"
  - "sync_per_container"
  - "stdext::sync_per_container"
  - "allocators/stdext::sync_per_container"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_per_container (classe)"
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# sync_per_container, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un [filtre de synchronisation](../standard-library/allocators-header.md) qui fournit un objet cache distinct pour chaque objet d'allocation.  
  
## Syntaxe  
  
```  
template <class Cache> class sync_per_container  
    : public Cache  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Cache`|Le type de cache associé au filtre de synchronisation.  Cela peut être [cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md), ou [cache\_suballoc](../standard-library/cache-suballoc-class.md).|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[equals](../Topic/sync_per_container::equals.md)|Compare si deux caches sont égaux.|  
  
## Configuration requise  
 **En\-tête :** \<allocateurs\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<allocators\>](../standard-library/allocators-header.md)