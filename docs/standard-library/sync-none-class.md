---
title: "sync_none, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext.sync_none"
  - "sync_none"
  - "allocators/stdext::sync_none"
  - "stdext::sync_none"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_none (classe)"
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# sync_none, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit [filtre de synchronisation](../standard-library/allocators-header.md) qui ne fournit aucune synchronisation.  
  
## Syntaxe  
  
```  
template <class Cache> class sync_none  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Cache`|Type de cache associé au filtre de synchronisation.  Cela peut être [cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md), ou [cache\_suballoc](../standard-library/cache-suballoc-class.md).|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[allouez](../Topic/sync_none::allocate.md)|Alloue un bloc de mémoire.|  
|[libérez](../Topic/sync_none::deallocate.md)|Libère un nombre spécifié d'objets de début de stockage à une position spécifiée.|  
|[equals](../Topic/sync_none::equals.md)|Compare deux caches en termes de égalité.|  
  
## Configuration requise  
 **En\-tête :**allocateurs \<de \>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<allocators\>](../standard-library/allocators-header.md)