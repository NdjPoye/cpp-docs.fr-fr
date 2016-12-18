---
title: "max_fixed_size, classe | Microsoft Docs"
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
  - "allocators/stdext::max_fixed_size"
  - "max_fixed_size"
  - "stdext::max_fixed_size"
  - "stdext.max_fixed_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_fixed_size (classe)"
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# max_fixed_size, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet d'[classe maximale](../standard-library/allocators-header.md) qui limite objet d'[freelist](../standard-library/freelist-class.md) à une longueur maximale fixe.  
  
## Syntaxe  
  
```  
template <std::size_t Max> class max_fixed_size  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Max`|La classe maximale qui détermine le nombre maximal d'éléments pour stockez dans `freelist`.|  
  
### Constructeurs  
  
|||  
|-|-|  
|[max\_fixed\_size](../Topic/max_fixed_size::max_fixed_size.md)|Construit un objet de type `max_fixed_size`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[alloué](../Topic/max_fixed_size::allocated.md)|Incrémente le nombre de blocs de mémoire alloués.|  
|[libéré](../Topic/max_fixed_size::deallocated.md)|Décrémente le nombre de blocs de mémoire alloués.|  
|[complète](../Topic/max_fixed_size::full.md)|Retourne une valeur qui spécifie si des blocs de mémoire doivent être ajoutés à la liste.|  
|[finale](../Topic/max_fixed_size::released.md)|Décrémente le nombre de blocs de mémoire sur la liste libre.|  
|[inscrit](../Topic/max_fixed_size::saved.md)|Incrémente le nombre de blocs de mémoire sur la liste libre.|  
  
## Configuration requise  
 **En\-tête :**allocateurs \<de \>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<allocators\>](../standard-library/allocators-header.md)