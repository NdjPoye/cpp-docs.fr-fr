---
title: "sync_shared, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sync_shared"
  - "allocators/stdext::sync_shared"
  - "stdext.sync_shared"
  - "stdext::sync_shared"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_shared (classe)"
ms.assetid: cab3af9e-3d1a-4f2c-8580-0f89e5687d8e
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# sync_shared, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un [filtre de synchronisation](../standard-library/allocators-header.md) qui utilise un mutex pour contrôler l'accès à un objet de cache partagé par tous les allocateurs.  
  
## Syntaxe  
  
```  
template <class Cache> class sync_shared  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Cache`|Type de cache associé au filtre de synchronisation. Il peut s'agir de [cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md) ou [cache\_suballoc](../standard-library/cache-suballoc-class.md).|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[allocate](../Topic/sync_shared::allocate.md)|Alloue un bloc de mémoire.|  
|[deallocate](../Topic/sync_shared::deallocate.md)|Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.|  
|[equals](../Topic/sync_shared::equals.md)|Compare l'égalité de deux caches.|  
  
## Configuration requise  
 **En\-tête :** \<allocators\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<allocators\>](../standard-library/allocators-header.md)