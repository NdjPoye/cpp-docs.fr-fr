---
title: "rts_alloc, classe | Microsoft Docs"
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
  - "stdext::rts_alloc"
  - "allocators/stdext::rts_alloc"
  - "rts_alloc"
  - "stdext.rts_alloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rts_alloc (classe)"
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rts_alloc, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle rts\_alloc décrit un [filtre](../standard-library/allocators-header.md) qui contient un tableau d'instances de cache et détermine quelle instance utiliser pour l'allocation et la désallocation au moment de l'exécution plutôt qu'au moment de la compilation.  
  
## Syntaxe  
  
```  
template <class Cache> class rts_alloc  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Cache`|Type d'instances de cache contenu dans le tableau.  Il peut s'agir de [cache\_chunklist, classe](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md) ou [cache\_suballoc](../standard-library/cache-suballoc-class.md).|  
  
## Notes  
 Cette classe de modèle contient plusieurs instances d'allocateur de bloc et détermine quelle instance utiliser pour l'allocation ou la désallocation au moment de l'exécution plutôt qu'au moment de la compilation.  Elle est utilisée avec les compilateurs qui ne peuvent pas compiler la reliaison.  
  
### Fonctions membres  
  
|||  
|-|-|  
|[allocate](../Topic/rts_alloc::allocate.md)|Alloue un bloc de mémoire.|  
|[deallocate](../Topic/rts_alloc::deallocate.md)|Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.|  
|[equals](../Topic/rts_alloc::equals.md)|Compare l'égalité de deux caches.|  
  
## Configuration requise  
 **En\-tête :** \<allocators\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md)   
 [\<allocators\>](../standard-library/allocators-header.md)