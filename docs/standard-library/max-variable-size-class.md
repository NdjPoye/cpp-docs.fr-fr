---
title: "max_variable_size, classe | Microsoft Docs"
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
  - "stdext::max_variable_size"
  - "allocators/stdext::max_variable_size"
  - "stdext.max_variable_size"
  - "max_variable_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_variable_size (classe)"
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# max_variable_size, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un [max classe](../standard-library/allocators-header.md) objet qui limite un [freelist](../standard-library/freelist-class.md) d’allouer l’objet d’une longueur maximale proportionnelle à peu près au nombre de blocs de mémoire.  
  
## Syntaxe  
  
```  
class max_variable_size  
```  
  
### Constructeurs  
  
|||  
|-|-|  
|[max\_variable\_size](../Topic/max_variable_size::max_variable_size.md)|Construit un objet de type `max_variable_size`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[alloué](../Topic/max_variable_size::allocated.md)|Incrémente le nombre de blocs de mémoire allouée.|  
|[désalloué](../Topic/max_variable_size::deallocated.md)|Décrémente le nombre d’alloué des blocs de mémoire.|  
|[complète](../Topic/max_variable_size::full.md)|Retourne une valeur qui indique si plusieurs blocs de mémoire doivent être ajoutés à la liste libre.|  
|[publié](../Topic/max_variable_size::released.md)|Décrémente le nombre de mémoire se bloque sur la liste libre.|  
|[enregistré](../Topic/max_variable_size::saved.md)|Incrémente le nombre de blocs de mémoire dans la liste libre.|  
  
## Configuration requise  
 **En\-tête :** \<allocators\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<allocators\>](../standard-library/allocators-header.md)