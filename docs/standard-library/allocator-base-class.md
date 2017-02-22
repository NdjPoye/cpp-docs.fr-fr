---
title: "allocator_base, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators.allocator_base"
  - "stdext.allocators.allocator_base"
  - "allocator_base"
  - "allocators/stdext::allocator_base"
  - "stdext::allocator_base"
  - "stdext::allocators::allocator_base"
  - "allocators/stdext::allocators::allocator_base"
  - "allocators::allocator_base"
  - "stdext.allocator_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_base (classe)"
ms.assetid: f920b45f-2a88-4bb0-8ead-b6126b426ed4
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# allocator_base, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit la classe de base et les fonctions communes nécessaires à la création d'un allocateur défini par l'utilisateur à partir d'un filtre de synchronisation.  
  
## Syntaxe  
  
```  
template <class Type, class Sync> class allocator_base  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Type`|Type des éléments alloués par l'allocateur.|  
|`Sync`|Stratégie de synchronisation de l'allocateur, qui est [sync\_none, classe](../standard-library/sync-none-class.md), [sync\_per\_container, classe](../standard-library/sync-per-container-class.md), [sync\_per\_thread, classe](../standard-library/sync-per-thread-class.md) ou [sync\_shared, classe](../standard-library/sync-shared-class.md).|  
  
### Constructeurs  
  
|||  
|-|-|  
|[allocator\_base](../Topic/allocator_base::allocator_base.md)|Construit un objet de type `allocator_base`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[const\_pointer](../Topic/allocator_base::const_pointer.md)|Type qui fournit un pointeur constant vers le type d'objet géré par l'allocateur.|  
|[const\_reference](../Topic/allocator_base::const_reference.md)|Type qui fournit une référence constante au type d'objet géré par l'allocateur.|  
|[difference\_type](../Topic/allocator_base::difference_type.md)|Type intégral signé qui peut représenter la différence entre des valeurs de pointeurs vers le type d'objet géré par l'allocateur.|  
|[pointer](../Topic/allocator_base::pointer.md)|Type qui fournit un pointeur vers le type d'objet géré par l'allocateur.|  
|[référence](../Topic/allocator_base::reference.md)|Type qui fournit une référence au type d'objet géré par l'allocateur.|  
|[type\_taille](../Topic/allocator_base::size_type.md)|Type intégral non signé qui peut représenter la longueur d'une séquence qu'un objet de classe de modèle `allocator_base` peut allouer.|  
|[value\_type](../Topic/allocator_base::value_type.md)|Type géré par l'allocateur.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[\_Charalloc](../Topic/allocator_base::_Charalloc.md)|Alloue du stockage pour un tableau de type `char`.|  
|[\_Chardealloc](../Topic/allocator_base::_Chardealloc.md)|Libère du stockage pour le tableau contenant des éléments de type `char`.|  
|[adresse](../Topic/allocator_base::address.md)|Recherche l'adresse d'un objet dont la valeur est spécifiée.|  
|[allocate](../Topic/allocator_base::allocate.md)|Alloue un bloc de mémoire suffisamment grand pour stocker au moins un nombre spécifié d'éléments.|  
|[construct](../Topic/allocator_base::construct.md)|Construit un type d'objet spécifique à une adresse spécifiée qui est initialisée avec une valeur spécifiée.|  
|[deallocate](../Topic/allocator_base::deallocate.md)|Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.|  
|[destroy](../Topic/allocator_base::destroy.md)|Appelle un destructeur d'objets sans libérer la mémoire où l'objet était stocké.|  
|[max\_size](../Topic/allocator_base::max_size.md)|Retourne le nombre d'éléments de type `Type` qui pourraient être alloués par un objet d'allocateur de classe avant que la mémoire libre soit complètement utilisée.|  
  
## Configuration requise  
 **En\-tête :** \<allocators\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<allocators\>](../standard-library/allocators-header.md)