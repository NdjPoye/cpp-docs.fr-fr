---
title: "max_unbounded, classe | Microsoft Docs"
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
  - "allocators/stdext::max_unbounded"
  - "stdext::max_unbounded"
  - "stdext.max_unbounded"
  - "max_unbounded"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_unbounded (classe)"
ms.assetid: e34627a9-c231-4031-a483-cbb0514fff46
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# max_unbounded, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un [max classe](../standard-library/allocators-header.md) objet qui ne limite pas la longueur maximale d’un [freelist](../standard-library/freelist-class.md) objet.  
  
## Syntaxe  
  
```  
class max_unbounded  
```  
  
### Fonctions membres  
  
|||  
|-|-|  
|[alloué](../Topic/max_unbounded::allocated.md)|Incrémente le nombre de blocs de mémoire allouée.|  
|[désalloué](../Topic/max_unbounded::deallocated.md)|Décrémente le nombre d’alloué des blocs de mémoire.|  
|[complète](../Topic/max_unbounded::full.md)|Retourne une valeur qui indique si plusieurs blocs de mémoire doivent être ajoutés à la liste libre.|  
|[publié](../Topic/max_unbounded::released.md)|Décrémente le nombre de mémoire se bloque sur la liste libre.|  
|[enregistré](../Topic/max_unbounded::saved.md)|Incrémente le nombre de blocs de mémoire dans la liste libre.|  
  
## Configuration requise  
 **En\-tête :** \<allocators\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<allocators\>](../standard-library/allocators-header.md)