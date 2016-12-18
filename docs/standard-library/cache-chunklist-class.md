---
title: "cache_chunklist, classe | Microsoft Docs"
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
  - "allocators/stdext::cache_chunklist"
  - "stdext.cache_chunklist"
  - "stdext::cache_chunklist"
  - "cache_chunklist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache_chunklist (classe)"
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
caps.latest.revision: 17
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# cache_chunklist, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit [allocateur de bloc](../standard-library/allocators-header.md) pour allouer et libérer des blocs de mémoire d'une seule taille.  
  
## Syntaxe  
  
```  
template <std::size_t Sz, std::size_t Nelts = 20> class cache_chunklist  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Sz`|Le nombre d'éléments dans le tableau à allouer.|  
  
## Notes  
 Cette classe de modèle utilise `operator new` pour allouer les segments de mémoire brute, suballocating blocages à allouer le stockage d'un bloc de mémoire au moment voulu ; enregistre les blocs de mémoire libérés dans une liste libre distincte pour chaque segment, et utilise `operator delete` pour libérer un segment lorsqu'aucun de ses blocs de mémoire n'est utilisé.  
  
 Chaque bloc de mémoire contient les octets d'`Sz` de mémoire utilisable et un pointeur vers le segment qu'il appartient.  Chaque segment contient les blocs de mémoire d'`Nelts`, trois pointeurs, int et les données qu' `operator new` et `operator delete` requièrent.  
  
### Constructeurs  
  
|||  
|-|-|  
|[cache\_chunklist](../Topic/cache_chunklist::cache_chunklist.md)|Construit un objet de type `cache_chunklist`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[allouez](../Topic/cache_chunklist::allocate.md)|Alloue un bloc de mémoire.|  
|[libérez](../Topic/cache_chunklist::deallocate.md)|Libère un nombre spécifié d'objets de début de stockage à une position spécifiée.|  
  
## Configuration requise  
 **En\-tête :**allocateurs \<de \>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<allocators\>](../standard-library/allocators-header.md)