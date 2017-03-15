---
title: "cache_freelist, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext.cache_freelist"
  - "allocators/stdext::cache_freelist"
  - "stdext::cache_freelist"
  - "cache_freelist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache_freelist (classe)"
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# cache_freelist, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit un [Bloquer allocateur](../standard-library/allocators-header.md) qui alloue et libère de blocs de mémoire d’une taille unique.  
  
## Syntaxe  
  
```  
template <std::size_t Sz, class Max> class cache_freelist  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Sz`|Le nombre d’éléments dans le tableau à allouer.|  
|`Max`|La classe max représentant la taille maximale de la liste libre. Cela peut être [max\_fixed\_size](../standard-library/max-fixed-size-class.md), [max\_none](../standard-library/max-none-class.md), [max\_unbounded](../standard-library/max-unbounded-class.md), ou [max\_variable\_size](../standard-library/max-variable-size-class.md).|  
  
## Notes  
 La classe de modèle cache\_freelist conserve une liste libre de blocs de mémoire de taille `Sz`. Lorsque la liste libre est plein, il utilise `operator delete` pour libérer la mémoire bloque. Lorsque la liste libre est vide, il utilise `operator new` pour allouer de nouveaux blocs de mémoire. La taille maximale de la liste libre est déterminée par la classe classe max passée dans le `Max` paramètre.  
  
 Chaque bloc de mémoire conserve `Sz` octets de mémoire utilisable et les données qui `operator new` et `operator delete` requièrent.  
  
### Constructeurs  
  
|||  
|-|-|  
|[cache\_freelist](../Topic/cache_freelist::cache_freelist.md)|Construit un objet de type `cache_freelist`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[allocate](../Topic/cache_freelist::allocate.md)|Alloue un bloc de mémoire.|  
|[deallocate](../Topic/cache_freelist::deallocate.md)|Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.|  
  
## Configuration requise  
 **En\-tête :** \<allocators\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<allocators\>](../standard-library/allocators-header.md)