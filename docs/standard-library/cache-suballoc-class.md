---
title: "cache_suballoc, classe | Microsoft Docs"
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
  - "stdext.cache_suballoc"
  - "allocators/stdext::cache_suballoc"
  - "stdext::cache_suballoc"
  - "cache_suballoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache_suballoc (classe)"
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
caps.latest.revision: 17
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# cache_suballoc, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit un [Bloquer allocateur](../standard-library/allocators-header.md) qui alloue et libère de blocs de mémoire d’une taille unique.  
  
## Syntaxe  
  
```  
template <std::size_t Sz, size_t Nelts = 20> class cache_suballoc  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Sz`|Le nombre d’éléments dans le tableau à allouer.|  
  
## Notes  
 La classe de modèle cache\_suballoc stocke les blocs de mémoire libérée dans une liste libre avec une longueur illimitée, à l’aide de `freelist<sizeof(Type), max_unbounded>`, et suballocates des blocs de mémoire d’une plus grande partie allouée avec `operator new` lorsque la liste libre est vide.  
  
 Chaque segment conserve `Sz * Nelts` octets de mémoire utilisable et les données qui `operator new` et `operator delete` requièrent. Segments alloués ne sont jamais libérés.  
  
### Constructeurs  
  
|||  
|-|-|  
|[cache\_suballoc](../Topic/cache_suballoc::cache_suballoc.md)|Construit un objet de type `cache_suballoc`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[allocate](../Topic/cache_suballoc::allocate.md)|Alloue un bloc de mémoire.|  
|[deallocate](../Topic/cache_suballoc::deallocate.md)|Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.|  
  
## Configuration requise  
 **En\-tête :** \<allocators\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<allocators\>](../standard-library/allocators-header.md)