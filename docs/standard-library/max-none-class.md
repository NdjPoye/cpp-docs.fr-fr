---
title: "max_none, classe | Microsoft Docs"
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
  - "max_none"
  - "stdext::max_none"
  - "stdext.max_none"
  - "allocators/stdext::max_none"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_none (classe)"
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# max_none, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un [max classe](../standard-library/allocators-header.md) objet qui limite un [freelist](../standard-library/freelist-class.md) objet à une longueur maximale de zéro.  
  
## Syntaxe  
  
```  
template <std::size_t Max> class max_none  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Max`|La classe maximale qui détermine le nombre maximal d’éléments à stocker dans le `freelist`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[alloué](../Topic/max_none::allocated.md)|Incrémente le nombre de blocs de mémoire allouée.|  
|[désalloué](../Topic/max_none::deallocated.md)|Décrémente le nombre d’alloué des blocs de mémoire.|  
|[complète](../Topic/max_none::full.md)|Retourne une valeur qui indique si plusieurs blocs de mémoire doivent être ajoutés à la liste libre.|  
|[publié](../Topic/max_none::released.md)|Décrémente le nombre de mémoire se bloque sur la liste libre.|  
|[enregistré](../Topic/max_none::saved.md)|Incrémente le nombre de blocs de mémoire dans la liste libre.|  
  
## Configuration requise  
 **En\-tête :** \<allocators\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<allocators\>](../standard-library/allocators-header.md)