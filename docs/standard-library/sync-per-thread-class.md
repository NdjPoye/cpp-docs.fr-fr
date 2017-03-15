---
title: "sync_per_thread, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::sync_per_thread"
  - "sync_per_thread"
  - "allocators/stdext::sync_per_thread"
  - "stdext.sync_per_thread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_per_thread (classe)"
ms.assetid: 47bf75f8-5b02-4760-b1d3-3099d08fe14c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# sync_per_thread, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un [filtre de synchronisation](../standard-library/allocators-header.md) qui fournit un objet cache distinct pour chaque thread.  
  
## Syntaxe  
  
```  
template <class Cache> class sync_per_thread  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Cache`|Le type de cache associé au filtre de synchronisation.  Cela peut être [cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md), ou [cache\_suballoc](../standard-library/cache-suballoc-class.md).|  
  
## Notes  
 Les allocateurs qui utilisent `sync_per_thread` peuvent être comparer égaux bien que les blocs propriétaires dans un thread ne peuvent pas être libérés depuis un autre thread.  Lors de l'utilisation de l'un de ces blocs de mémoire d'allocateurs alloués dans un thread ne doit pas être rendue visible à d'autres threads.  Dans la pratique cela signifie qu'un conteneur qui utilise un de ces allocateurs doit être accessible par un thread unique.  
  
### Fonctions membres  
  
|||  
|-|-|  
|[allocate](../Topic/sync_per_thread::allocate.md)|Alloue un bloc de mémoire.|  
|[libérer](../Topic/sync_per_thread::deallocate.md)|Libère un nombre spécifié d'objets depuis le début de stockage à une position spécifiée.|  
|[equals](../Topic/sync_per_thread::equals.md)|Compare si deux caches sont égaux.|  
  
## Configuration requise  
 **En\-tête :** \<allocateurs\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<allocators\>](../standard-library/allocators-header.md)