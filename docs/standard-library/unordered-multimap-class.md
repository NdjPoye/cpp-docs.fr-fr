---
title: "unordered_multimap, classe | Microsoft Docs"
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
  - "unordered_map/std::tr1::unordered_multimap"
  - "tr1.unordered_multimap"
  - "unordered_multimap"
  - "std.tr1.unordered_multimap"
  - "tr1::unordered_multimap"
  - "std::tr1::unordered_multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unordered_multimap (classe)"
  - "unordered_multimap (classe) (TR1)"
ms.assetid: 4baead6c-5870-4b85-940f-a47d6b891c27
caps.latest.revision: 28
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# unordered_multimap, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle décrit un objet qui contrôle une séquence de longueur variable constituée d'éléments de type `std::pair<const Key, Ty>`.  La séquence est triée par ordre faible avec une fonction de hachage, qui partitionne la séquence en un ensemble trié de sous\-séquences appelées compartiments.  Dans chaque compartiment, une fonction de comparaison détermine si des paires d'éléments possèdent un ordre équivalent.  Chaque élément stocke deux objets, une clé de tri et une valeur.  La séquence est représentée de façon à permettre la recherche, l'insertion et la suppression d'un élément arbitraire à l'aide d'un certain nombre d'opérations qui peut être indépendant du nombre d'éléments de la séquence \(temps constant\), du moins lorsque les compartiments sont de longueur à peu près équivalente.  Dans le pire des cas, lorsque tous les éléments se trouvent dans un compartiment, le nombre d'opérations est proportionnel au nombre d'éléments de la séquence \(temps linéaire\).  De plus, l'insertion d'un élément n'entraîne pas la non validité des itérateurs, et la suppression d'un élément ne rend non valides que les itérateurs qui pointent vers l'élément supprimé.  
  
## Syntaxe  
  
```  
template<class Key,  
    class Ty,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<Key> >  
    class unordered_multimap;  
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
|[unordered\_multimap::allocator\_type](../Topic/unordered_multimap::allocator_type.md)|Type d'un allocateur pour la gestion du stockage.|  
|[unordered\_multimap::const\_iterator](../Topic/unordered_multimap::const_iterator.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[unordered\_multimap::const\_local\_iterator](../Topic/unordered_multimap::const_local_iterator.md)|Type d'un itérateur de compartiment constant pour la séquence contrôlée.|  
|[unordered\_multimap::const\_pointer](../Topic/unordered_multimap::const_pointer.md)|Type d'un pointeur constant vers un élément.|  
|[unordered\_multimap::const\_reference](../Topic/unordered_multimap::const_reference.md)|Type d'une référence constante à un élément.|  
|[unordered\_multimap::difference\_type](../Topic/unordered_multimap::difference_type.md)|Type d'une distance signée entre deux éléments.|  
|[unordered\_multimap::hasher](../Topic/unordered_multimap::hasher.md)|Type de la fonction de hachage.|  
|[unordered\_multimap::iterator](../Topic/unordered_multimap::iterator.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[unordered\_multimap::key\_equal](../Topic/unordered_multimap::key_equal.md)|Type de la fonction de comparaison.|  
|[unordered\_multimap::key\_type](../Topic/unordered_multimap::key_type.md)|Type d'une clé de tri.|  
|[unordered\_multimap::local\_iterator](../Topic/unordered_multimap::local_iterator.md)|Type d'un itérateur de compartiment pour la séquence contrôlée.|  
|[unordered\_multimap::mapped\_type](../Topic/unordered_multimap::mapped_type.md)|Type d'une valeur mappée associée à chaque clé.|  
|[unordered\_multimap::pointer](../Topic/unordered_multimap::pointer.md)|Type d'un pointeur vers un élément.|  
|[unordered\_multimap::reference](../Topic/unordered_multimap::reference.md)|Type d'une référence à un élément.|  
|[unordered\_multimap::size\_type](../Topic/unordered_multimap::size_type.md)|Type d'une distance non signée entre deux éléments.|  
|[unordered\_multimap::value\_type](../Topic/unordered_multimap::value_type.md)|Type d'un élément.|  
  
|||  
|-|-|  
|Fonction membre|Description|  
|[unordered\_multimap::begin](../Topic/unordered_multimap::begin.md)|Désigne le début de la séquence contrôlée.|  
|[unordered\_multimap::bucket](../Topic/unordered_multimap::bucket.md)|Obtient le numéro du compartiment pour une valeur de clé.|  
|[unordered\_multimap::bucket\_count](../Topic/unordered_multimap::bucket_count.md)|Obtient le nombre de compartiments.|  
|[unordered\_multimap::bucket\_size](../Topic/unordered_multimap::bucket_size.md)|Obtient la taille d'un compartiment.|  
|[unordered\_multimap::cbegin](../Topic/unordered_multimap::cbegin.md)|Désigne le début de la séquence contrôlée.|  
|[unordered\_multimap::cend](../Topic/unordered_multimap::cend.md)|Désigne la fin de la séquence contrôlée.|  
|[unordered\_multimap::clear](../Topic/unordered_multimap::clear.md)|Supprime tous les éléments.|  
|[unordered\_multimap::count](../Topic/unordered_multimap::count.md)|Recherche le nombre d'éléments qui correspondent à une clé spécifiée.|  
|[unordered\_multimap::emplace](../Topic/unordered_multimap::emplace.md)|Ajoute un élément construit sur place.|  
|[unordered\_multimap::emplace\_hint](../Topic/unordered_multimap::emplace_hint.md)|Ajoute un élément construit sur place, avec un indicateur.|  
|[unordered\_multimap::empty](../Topic/unordered_multimap::empty.md)|Vérifie l'absence d'éléments.|  
|[unordered\_multimap::end](../Topic/unordered_multimap::end.md)|Désigne la fin de la séquence contrôlée.|  
|[unordered\_multimap::equal\_range](../Topic/unordered_multimap::equal_range.md)|Recherche une plage qui correspond à une clé spécifiée.|  
|[unordered\_multimap::erase](../Topic/unordered_multimap::erase.md)|Supprime les éléments placés aux positions spécifiées.|  
|[unordered\_multimap::find](../Topic/unordered_multimap::find.md)|Recherche un élément qui correspond à une clé spécifiée.|  
|[unordered\_multimap::get\_allocator](../Topic/unordered_multimap::get_allocator.md)|Obtient l'objet allocateur stocké.|  
|[unordered\_multimap::hash\_function](../Topic/unordered_multimap::hash_function.md)|Obtient l'objet de fonction de hachage stocké.|  
|[unordered\_multimap::insert](../Topic/unordered_multimap::insert.md)|Ajoute des éléments.|  
|[unordered\_multimap::key\_eq](../Topic/unordered_multimap::key_eq.md)|Obtient l'objet de fonction de comparaison stocké.|  
|[unordered\_multimap::load\_factor](../Topic/unordered_multimap::load_factor.md)|Compte le nombre moyen d'éléments par compartiment.|  
|[unordered\_multimap::max\_bucket\_count](../Topic/unordered_multimap::max_bucket_count.md)|Obtient le nombre maximal de compartiments.|  
|[unordered\_multimap::max\_load\_factor](../Topic/unordered_multimap::max_load_factor.md)|Obtient ou définit le nombre maximal d'éléments par compartiment.|  
|[unordered\_multimap::max\_size](../Topic/unordered_multimap::max_size.md)|Obtient ou définit la taille maximale de la séquence contrôlée.|  
|[unordered\_multimap::rehash](../Topic/unordered_multimap::rehash.md)|Régénère la table de hachage.|  
|[unordered\_multimap::size](../Topic/unordered_multimap::size.md)|Compte le nombre d'éléments.|  
|[unordered\_multimap::swap](../Topic/unordered_multimap::swap.md)|Échange le contenu de deux conteneurs.|  
|[unordered\_multimap::unordered\_multimap](../Topic/unordered_multimap::unordered_multimap.md)|Construit un objet conteneur.|  
  
|||  
|-|-|  
|Opérateur|Description|  
|[unordered\_multimap::operator\=](../Topic/unordered_multimap::operator=.md)|Copie une table de hachage.|  
  
## Notes  
 L'objet trie la séquence qu'il contrôle en appelant deux objets stockés, un objet de fonction de comparaison de type [unordered\_multimap::key\_equal](../Topic/unordered_multimap::key_equal.md) et un objet de fonction de hachage de type [unordered\_multimap::hasher](../Topic/unordered_multimap::hasher.md).  Pour accéder au premier objet stocké, appelez la fonction membre [unordered\_multimap::key\_eq](../Topic/unordered_multimap::key_eq.md)`()`. Pour accéder au second objet stocké, appelez la fonction membre [unordered\_multimap::hash\_function](../Topic/unordered_multimap::hash_function.md)`()`.  Pour toutes les valeurs `X` et `Y` de type `Key`, l'appel `key_eq()(X, Y)` retourne true uniquement si les valeurs des deux arguments ont un classement équivalent. L'appel `hash_function()(keyval)` génère une distribution des valeurs de type `size_t`.  Contrairement à la classe de modèle [unordered\_map, classe](../standard-library/unordered-map-class.md), un objet de classe de modèle `unordered_multimap` ne garantit pas que `key_eq()(X, Y)` est toujours false pour deux des éléments de la séquence contrôlée. Il n'est pas nécessaire que les clés soient uniques.  
  
 L'objet stocke également un facteur de charge maximale, qui spécifie le nombre moyen maximal d'éléments souhaité par compartiment.  Si après l'insertion d'un élément, [unordered\_multimap::load\_factor](../Topic/unordered_multimap::load_factor.md)`()` dépasse le facteur de charge maximale, le conteneur augmente le nombre de compartiments et régénère la table de hachage si nécessaire.  
  
 L'ordre réel des éléments de la séquence contrôlée dépend de la fonction de hachage, de la fonction de comparaison, de l'ordre d'insertion, du facteur de charge maximale et du nombre de compartiments.  En général, il n'est pas possible de prévoir l'ordre des éléments de la séquence contrôlée.  Toutefois, vous avez la garantie que tous les sous\-ensembles d'éléments dont le classement est équivalent sont adjacents dans la séquence contrôlée.  
  
 L'objet alloue et libère du stockage pour la séquence qu'il contrôle via un objet allocateur stocké de type [unordered\_multimap::allocator\_type](../Topic/unordered_multimap::allocator_type.md).  Un tel objet allocateur doit avoir la même interface externe qu'un objet de classe de modèle `allocator`.  Notez que l'objet allocateur stocké n'est pas copié lorsque l'objet conteneur est assigné.  
  
## Configuration requise  
 **En\-tête :** \<unordered\_map\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<unordered\_map\>](../standard-library/unordered-map.md)   
 [Conteneurs](../cpp/containers-modern-cpp.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)