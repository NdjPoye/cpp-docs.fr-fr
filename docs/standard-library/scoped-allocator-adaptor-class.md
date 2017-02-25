---
title: "scoped_allocator_adaptor::construct, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.scoped_allocator_adaptor"
  - "scoped_allocator_adaptor"
  - "scoped_allocator/std::scoped_allocator_adaptor"
  - "std::scoped_allocator_adaptor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scoped_allocator_adaptor::construct, méthode"
ms.assetid: 0d9b06a1-9a4a-4669-9470-8805cae48e89
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# scoped_allocator_adaptor::construct, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un emboîtement d' allocateurs.  
  
## Syntaxe  
  
```cpp  
template<class Outer, class... Inner>  
    class scoped_allocator_adaptor;  
```  
  
## Notes  
 Le modèle de classe contient un emboîtement d'un ou plusieurs allocateurs.  Une telle classe possède un allocateur extérieur de type `outer_allocator_type`, un synonyme pour `Outer`, qui est une base publique de l'objet d' `scoped_allocator_adaptor`.  `Outer` est utilisée pour allouer de la mémoire à utiliser par un conteneur.  Vous pouvez obtenir une référence à cet objet de base d'allocateur en appelant `outer_allocator`.  
  
 Le reste de l'emboîtement est de type `inner_allocator_type`.  Un allocateur interne est utilisé pour allouer de la mémoire pour les éléments dans un conteneur.  Vous pouvez obtenir une référence à l'objet stockée de ce type en appelant `inner_allocator`.  Si `Inner...` n'est pas vide, `inner_allocator_type` est de type `scoped_allocator_adaptor<Inner...>`, et `inner_allocator` indique un objet membre.  Sinon, `inner_allocator_type` est de type `scoped_allocator_adaptor<Outer>`, et `inner_allocator` désigne l'objet entier.  
  
 L'emboîtement se comporte comme s'il avait une profondeur arbitraire, répliquant son allocateur encapsulé le plus profond si nécessaire.  
  
 Plusieurs concepts qui ne font pas partie de l'interface visible aident à décrire le comportement de ce modèle de classe.  *Un allocateur extérieur* gère tous les appels aux méthodes de construction et de destruction.  Il est efficacement défini par la fonction récursive `OUTERMOST(X)` où `OUTERMOST(X)` est l'une des valeurs suivantes.  
  
-   Si `X.outer_allocator()` a une forme correcte, alors `OUTERMOST(X)` si `OUTERMOST(X.outer_allocator())`.  
  
-   Sinon, `OUTERMOST(X)` est `X`.  
  
 Trois types sont définis par souci d'affichage :  
  
|Type|Description|  
|----------|-----------------|  
|`Outermost`|Type de `OUTERMOST(*this)`.|  
|`Outermost_traits`|`allocator_traits<Outermost>`|  
|`Outer_traits`|`allocator_traits<Outer>`|  
  
### Constructeurs  
  
|Nom|Description|  
|---------|-----------------|  
|[scoped\_allocator\_adaptor::scoped\_allocator\_adaptor, constructeur](../Topic/scoped_allocator_adaptor::scoped_allocator_adaptor%20Constructor.md)|Construit un objet `scoped_allocator_adaptor`.|  
  
### Typedef  
  
|Nom|Description|  
|---------|-----------------|  
|`const_pointer`|Ce type est un synonyme de `const_pointer` associé à l'allocateur `Outer`.|  
|`const_void_pointer`|Ce type est un synonyme de `const_void_pointer` associé à l'allocateur `Outer`.|  
|`difference_type`|Ce type est un synonyme de `difference_type` associé à l'allocateur `Outer`.|  
|`inner_allocator_type`|Ce type est un synonyme de type de l'adaptateur imbriqué `scoped_allocator_adaptor<Inner...>`.|  
|`outer_allocator_type`|Ce type est un synonyme de type de l'allocateur de base `Outer`.|  
|`pointer`|Ce type est un synonyme de `pointer` associé à l'allocateur `Outer`.|  
|`propagate_on_container_copy_assignment`|Le type reste vrai uniquement si `Outer_traits::propagate_on_container_copy_assignment` reste vrai ou d'`inner_allocator_type::propagate_on_container_copy_assignment` reste vrai.|  
|`propagate_on_container_move_assignment`|Le type reste vrai uniquement si `Outer_traits::propagate_on_container_move_assignment` reste vrai ou d'`inner_allocator_type::propagate_on_container_move_assignment` reste vrai|  
|`propagate_on_container_swap`|Le type reste vrai uniquement si `Outer_traits::propagate_on_container_swap` reste vrai ou d'`inner_allocator_type::propagate_on_container_swap` reste vrai.|  
|`size_type`|Ce type est un synonyme de `size_type` associé à l'allocateur `Outer`.|  
|`value_type`|Ce type est un synonyme de `value_type` associé à l'allocateur `Outer`.|  
|`void_pointer`|Ce type est un synonyme de `void_pointer` associé à l'allocateur `Outer`.|  
  
### Structures  
  
|Nom|Description|  
|---------|-----------------|  
|[scoped\_allocator\_adaptor::rebind, struct](../Topic/scoped_allocator_adaptor::rebind%20Struct.md)|Définit le type `Outer::rebind<Other>::other` comme synonyme de `scoped_allocator_adaptor<Other, Inner...>`.|  
  
### Méthodes  
  
|Nom|Description|  
|---------|-----------------|  
|[scoped\_allocator\_adaptor::allocate, méthode](../Topic/scoped_allocator_adaptor::allocate%20Method.md)|Alloue la mémoire à l'aide de l'allocateur d'`Outer`.|  
|[scoped\_allocator\_adaptor::construct, méthode](../Topic/scoped_allocator_adaptor::construct%20Method.md)|Construit un objet .|  
|[scoped\_allocator\_adaptor::deallocate, méthode](../Topic/scoped_allocator_adaptor::deallocate%20Method.md)|Libère des objets à l'aide de l'allocateur externe.|  
|[scoped\_allocator\_adaptor::destroy, méthode](../Topic/scoped_allocator_adaptor::destroy%20Method.md)|Détruit un objet spécifié.|  
|[scoped\_allocator\_adaptor::inner\_allocator, méthode](../Topic/scoped_allocator_adaptor::inner_allocator%20Method.md)|Récupère une référence à l'objet stocké de type `inner_allocator_type`.|  
|[scoped\_allocator\_adaptor::max\_size, méthode](../Topic/scoped_allocator_adaptor::max_size%20Method.md)|Détermine le nombre maximal d'objets qui peuvent être alloués par l'allocateur externe.|  
|[scoped\_allocator\_adaptor::outer\_allocator, méthode](../Topic/scoped_allocator_adaptor::outer_allocator%20Method.md)|Récupère une référence à l'objet stocké de type `outer_allocator_type`.|  
|[scoped\_allocator\_adaptor::select\_on\_container\_copy\_construction, méthode](../Topic/scoped_allocator_adaptor::select_on_container_copy_construction%20Method.md)|Crée un nouvel objet d'`scoped_allocator_adaptor` avec chaque allocateur stocké initialisé en appelant `select_on_container_copy_construction` pour chaque allocateur correspondant.|  
  
## Configuration requise  
 **En\-tête:** \<scoped\_allocator\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)