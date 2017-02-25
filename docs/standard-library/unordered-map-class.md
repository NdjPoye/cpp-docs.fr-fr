---
title: "unordered_map, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::unordered_map"
  - "std.tr1.unordered_map"
  - "tr1.unordered_map"
  - "tr1::unordered_map"
  - "unordered_map"
  - "unordered_map/std::tr1::unordered_map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unordered_map (classe)"
  - "unordered_map (classe) (TR1)"
ms.assetid: 7cf7cfa1-16e7-461c-a9b2-3b8d8ec24e0d
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# unordered_map, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle décrit un objet qui contrôle une séquence de longueur variable constituée d'éléments de type `std::pair<const Key, Ty>`.  La séquence est triée par ordre faible avec une fonction de hachage, qui partitionne la séquence en un ensemble trié de sous\-séquences appelées compartiments.  Dans chaque compartiment, une fonction de comparaison détermine si des paires d'éléments possèdent un ordre équivalent.  Chaque élément stocke deux objets, une clé de tri et une valeur.  La séquence est représentée de façon à permettre la recherche, l'insertion et la suppression d'un élément arbitraire à l'aide d'un certain nombre d'opérations qui peut être indépendant du nombre d'éléments de la séquence \(temps constant\), du moins lorsque les compartiments sont de longueur à peu près équivalente.  Dans le pire des cas, lorsque tous les éléments se trouvent dans un compartiment, le nombre d'opérations est proportionnel au nombre d'éléments de la séquence \(temps linéaire\).  De plus, l'insertion d'un élément n'entraîne pas la non validité des itérateurs, et la suppression d'un élément ne rend non valides que les itérateurs qui pointent vers l'élément supprimé.  
  
## Syntaxe  
  
```  
template<class Key,  
    class Ty,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<std::pair<const Key, Ty> > >  
    class unordered_map;  
```  
  
#### Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`Key`|Type de clé.|  
|`Ty`|Type mappé.|  
|`Hash`|Type d'objet de la fonction de hachage.|  
|`Pred`|Type d'objet de fonction de comparaison d'égalité.|  
|`Alloc`|Classe allocator.|  
  
## Membres  
  
|||  
|-|-|  
|Définition de types|Description|  
|[unordered\_map::allocator\_type](../Topic/unordered_map::allocator_type.md)|Type d'un allocateur pour la gestion du stockage.|  
|[unordered\_map::const\_iterator](../Topic/unordered_map::const_iterator.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[unordered\_map::const\_local\_iterator](../Topic/unordered_map::const_local_iterator.md)|Type d'un itérateur de compartiment constant pour la séquence contrôlée.|  
|[unordered\_map::const\_pointer](../Topic/unordered_map::const_pointer.md)|Type d'un pointeur constant vers un élément.|  
|[unordered\_map::const\_reference](../Topic/unordered_map::const_reference.md)|Type d'une référence constante à un élément.|  
|[unordered\_map::difference\_type](../Topic/unordered_map::difference_type.md)|Type d'une distance signée entre deux éléments.|  
|[unordered\_map::hasher](../Topic/unordered_map::hasher.md)|Type de la fonction de hachage.|  
|[unordered\_map::iterator](../Topic/unordered_map::iterator.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[unordered\_map::key\_equal](../Topic/unordered_map::key_equal.md)|Type de la fonction de comparaison.|  
|[unordered\_map::key\_type](../Topic/unordered_map::key_type.md)|Type d'une clé de tri.|  
|[unordered\_map::local\_iterator](../Topic/unordered_map::local_iterator.md)|Type d'un itérateur de compartiment pour la séquence contrôlée.|  
|[unordered\_map::mapped\_type](../Topic/unordered_map::mapped_type.md)|Type d'une valeur mappée associée à chaque clé.|  
|[unordered\_map::pointer](../Topic/unordered_map::pointer.md)|Type d'un pointeur vers un élément.|  
|[unordered\_map::reference](../Topic/unordered_map::reference.md)|Type d'une référence à un élément.|  
|[unordered\_map::size\_type](../Topic/unordered_map::size_type.md)|Type d'une distance non signée entre deux éléments.|  
|[unordered\_map::value\_type](../Topic/unordered_map::value_type.md)|Type d'un élément.|  
  
|||  
|-|-|  
|Fonction membre|Description|  
|[unordered\_map::at](../Topic/unordered_map::at.md)|Recherche un élément avec la clé spécifiée.|  
|[unordered\_map::begin](../Topic/unordered_map::begin.md)|Désigne le début de la séquence contrôlée.|  
|[unordered\_map::bucket](../Topic/unordered_map::bucket.md)|Obtient le numéro du compartiment pour une valeur de clé.|  
|[unordered\_map::bucket\_count](../Topic/unordered_map::bucket_count.md)|Obtient le nombre de compartiments.|  
|[unordered\_map::bucket\_size](../Topic/unordered_map::bucket_size.md)|Obtient la taille d'un compartiment.|  
|[unordered\_map::cbegin](../Topic/unordered_map::cbegin.md)|Désigne le début de la séquence contrôlée.|  
|[unordered\_map::cend](../Topic/unordered_map::cend.md)|Désigne la fin de la séquence contrôlée.|  
|[unordered\_map::clear](../Topic/unordered_map::clear.md)|Supprime tous les éléments.|  
|[unordered\_map::count](../Topic/unordered_map::count.md)|Recherche le nombre d'éléments qui correspondent à une clé spécifiée.|  
|[unordered\_map::emplace](../Topic/unordered_map::emplace.md)|Ajoute un élément construit sur place.|  
|[unordered\_map::emplace\_hint](../Topic/unordered_map::emplace_hint.md)|Ajoute un élément construit sur place, avec un indicateur.|  
|[unordered\_map::empty](../Topic/unordered_map::empty.md)|Vérifie l'absence d'éléments.|  
|[unordered\_map::end](../Topic/unordered_map::end.md)|Désigne la fin de la séquence contrôlée.|  
|[unordered\_map::equal\_range](../Topic/unordered_map::equal_range.md)|Recherche une plage qui correspond à une clé spécifiée.|  
|[unordered\_map::erase](../Topic/unordered_map::erase.md)|Supprime les éléments placés aux positions spécifiées.|  
|[unordered\_map::find](../Topic/unordered_map::find.md)|Recherche un élément qui correspond à une clé spécifiée.|  
|[unordered\_map::get\_allocator](../Topic/unordered_map::get_allocator.md)|Obtient l'objet allocateur stocké.|  
|[unordered\_map::hash\_function](../Topic/unordered_map::hash_function.md)|Obtient l'objet de fonction de hachage stocké.|  
|[unordered\_map::insert](../Topic/unordered_map::insert.md)|Ajoute des éléments.|  
|[unordered\_map::key\_eq](../Topic/unordered_map::key_eq.md)|Obtient l'objet de fonction de comparaison stocké.|  
|[unordered\_map::load\_factor](../Topic/unordered_map::load_factor.md)|Compte le nombre moyen d'éléments par compartiment.|  
|[unordered\_map::max\_bucket\_count](../Topic/unordered_map::max_bucket_count.md)|Obtient le nombre maximal de compartiments.|  
|[unordered\_map::max\_load\_factor](../Topic/unordered_map::max_load_factor.md)|Obtient ou définit le nombre maximal d'éléments par compartiment.|  
|[unordered\_map::max\_size](../Topic/unordered_map::max_size.md)|Obtient ou définit la taille maximale de la séquence contrôlée.|  
|[unordered\_map::rehash](../Topic/unordered_map::rehash.md)|Régénère la table de hachage.|  
|[unordered\_map::size](../Topic/unordered_map::size.md)|Compte le nombre d'éléments.|  
|[unordered\_map::swap](../Topic/unordered_map::swap.md)|Échange le contenu de deux conteneurs.|  
|[unordered\_map::unordered\_map](../Topic/unordered_map::unordered_map.md)|Construit un objet conteneur.|  
  
|||  
|-|-|  
|Opérateur|Description|  
|[unordered\_map::operator](../Topic/unordered_map::operator.md)|Recherche ou insère un élément avec la clé spécifiée.|  
|[unordered\_map::operator\=](../Topic/unordered_map::operator=.md)|Copie une table de hachage.|  
  
## Notes  
 L'objet trie la séquence qu'il contrôle en appelant deux objets stockés, un objet de fonction de comparaison de type [unordered\_map::key\_equal](../Topic/unordered_map::key_equal.md) et un objet de fonction de hachage de type [unordered\_map::hasher](../Topic/unordered_map::hasher.md).  Pour accéder au premier objet stocké, appelez la fonction membre [unordered\_map::key\_eq](../Topic/unordered_map::key_eq.md)`()`. Pour accéder au second objet stocké, appelez la fonction membre [unordered\_map::hash\_function](../Topic/unordered_map::hash_function.md)`()`.  Pour toutes les valeurs `X` et `Y` de type `Key`, l'appel `key_eq()(X, Y)` retourne true uniquement si les valeurs des deux arguments ont un classement équivalent. L'appel `hash_function()(keyval)` génère une distribution des valeurs de type `size_t`.  Contrairement à la classe de modèle [unordered\_multimap, classe](../standard-library/unordered-multimap-class.md), un objet de classe de modèle `unordered_map` garantit que `key_eq()(X, Y)` a toujours la valeur false pour deux éléments quelconques de la séquence contrôlée. Les clés sont uniques.  
  
 L'objet stocke également un facteur de charge maximale, qui spécifie le nombre moyen maximal d'éléments souhaité par compartiment.  Si après l'insertion d'un élément, [unordered\_map::load\_factor](../Topic/unordered_map::load_factor.md)`()` dépasse le facteur de charge maximale, le conteneur augmente le nombre de compartiments et régénère la table de hachage si nécessaire.  
  
 L'ordre réel des éléments de la séquence contrôlée dépend de la fonction de hachage, de la fonction de comparaison, de l'ordre d'insertion, du facteur de charge maximale et du nombre de compartiments.  En général, il n'est pas possible de prévoir l'ordre des éléments de la séquence contrôlée.  Toutefois, vous avez la garantie que tous les sous\-ensembles d'éléments dont le classement est équivalent sont adjacents dans la séquence contrôlée.  
  
 L'objet alloue et libère du stockage pour la séquence qu'il contrôle via un objet allocateur stocké de type [unordered\_map::allocator\_type](../Topic/unordered_map::allocator_type.md).  Un tel objet allocateur doit avoir la même interface externe qu'un objet de classe de modèle `allocator`.  Notez que l'objet allocateur stocké n'est pas copié lorsque l'objet conteneur est assigné.  
  
## Configuration requise  
 **En\-tête :** \<unordered\_map\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<unordered\_map\>](../standard-library/unordered-map.md)   
 [Conteneurs](../cpp/containers-modern-cpp.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)