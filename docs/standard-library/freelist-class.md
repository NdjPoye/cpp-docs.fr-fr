---
title: "freelist, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::freelist"
  - "freelist"
  - "stdext.freelist"
  - "allocators/stdext::freelist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "freelist (classe)"
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# freelist, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gère une liste des blocs de mémoire.  
  
## Syntaxe  
  
```  
template <std::size_t Sz, class Max> class freelist  
    : public Max  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Sz`|Le nombre d'éléments dans le tableau à allouer.|  
|`Max`|La classe maximale qui représente le nombre maximal d'éléments à stocker dans la liste libre.  La classe maximale peut être [max\_none](../standard-library/max-none-class.md), [max\_unbounded](../standard-library/max-unbounded-class.md), [max\_fixed\_size](../standard-library/max-fixed-size-class.md), ou [max\_variable\_size](../standard-library/max-variable-size-class.md).|  
  
## Notes  
 Cette classe de modèle gère une liste des blocs de mémoire de taille `Sz` à la longueur maximale de la liste déterminée par la classe est transmise à `Max`.  
  
### Constructeurs  
  
|||  
|-|-|  
|[freelist](../Topic/freelist::freelist.md)|Construit un objet de type `freelist`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[pop](../Topic/freelist::pop.md)|Supprime le premier bloc de mémoire de la liste libre.|  
|[push](../Topic/freelist::push.md)|Ajoute un bloc de mémoire à la liste.|  
  
## Configuration requise  
 **En\-tête :**allocateurs \<de \>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<allocators\>](../standard-library/allocators-header.md)