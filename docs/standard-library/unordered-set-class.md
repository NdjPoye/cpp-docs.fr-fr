---
title: "unordered_set, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.unordered_set"
  - "std::tr1::unordered_set"
  - "unordered_set/std::tr1::unordered_set"
  - "tr1::unordered_set"
  - "unordered_set"
  - "tr1.unordered_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unordered_set (classe)"
  - "unordered_set (classe) (TR1)"
ms.assetid: ac08084e-05a7-48c0-9ae4-d40c529922dd
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# unordered_set, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle décrit un objet qui contrôle une séquence de longueur variable constituée d'éléments de type `const Key`.  La séquence est triée par ordre faible avec une fonction de hachage, qui partitionne la séquence en un ensemble trié de sous\-séquences appelées compartiments.  Dans chaque compartiment, une fonction de comparaison détermine si des paires d'éléments possèdent un ordre équivalent.  Chaque élément sert à la fois de clé de tri et de valeur.  La séquence est représentée de façon à permettre la recherche, l'insertion et la suppression d'un élément arbitraire à l'aide d'un certain nombre d'opérations qui peut être indépendant du nombre d'éléments de la séquence \(temps constant\), du moins lorsque les compartiments sont de longueur à peu près équivalente.  Dans le pire des cas, lorsque tous les éléments se trouvent dans un compartiment, le nombre d'opérations est proportionnel au nombre d'éléments de la séquence \(temps linéaire\).  De plus, l'insertion d'un élément n'entraîne pas la non validité des itérateurs, et la suppression d'un élément ne rend non valides que les itérateurs qui pointent vers l'élément supprimé.  
  
## Syntaxe  
  
```  
template<class Key,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<Key> >  
    class unordered_set;  
```  
  
#### Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`Key`|Type de clé.|  
|`Hash`|Type d'objet de la fonction de hachage.|  
|`Pred`|Type d'objet de fonction de comparaison d'égalité.|  
|`Alloc`|Classe allocator.|  
  
## Membres  
  
|||  
|-|-|  
|Définition de types|Description|  
|[unordered\_set::allocator\_type](../Topic/unordered_set::allocator_type.md)|Type d'un allocateur pour la gestion du stockage.|  
|[unordered\_set::const\_iterator](../Topic/unordered_set::const_iterator.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[unordered\_set::const\_local\_iterator](../Topic/unordered_set::const_local_iterator.md)|Type d'un itérateur de compartiment constant pour la séquence contrôlée.|  
|[unordered\_set::const\_pointer](../Topic/unordered_set::const_pointer.md)|Type d'un pointeur constant vers un élément.|  
|[unordered\_set::const\_reference](../Topic/unordered_set::const_reference.md)|Type d'une référence constante à un élément.|  
|[unordered\_set::difference\_type](../Topic/unordered_set::difference_type.md)|Type d'une distance signée entre deux éléments.|  
|[unordered\_set::hasher](../Topic/unordered_set::hasher.md)|Type de la fonction de hachage.|  
|[unordered\_set::iterator](../Topic/unordered_set::iterator.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[unordered\_set::key\_equal](../Topic/unordered_set::key_equal.md)|Type de la fonction de comparaison.|  
|[unordered\_set::key\_type](../Topic/unordered_set::key_type.md)|Type d'une clé de tri.|  
|[unordered\_set::local\_iterator](../Topic/unordered_set::local_iterator.md)|Type d'un itérateur de compartiment pour la séquence contrôlée.|  
|[unordered\_set::pointer](../Topic/unordered_set::pointer.md)|Type d'un pointeur vers un élément.|  
|[unordered\_set::reference](../Topic/unordered_set::reference.md)|Type d'une référence à un élément.|  
|[unordered\_set::size\_type](../Topic/unordered_set::size_type.md)|Type d'une distance non signée entre deux éléments.|  
|[unordered\_set::value\_type](../Topic/unordered_set::value_type.md)|Type d'un élément.|  
  
|||  
|-|-|  
|Fonction membre|Description|  
|[unordered\_set::begin](../Topic/unordered_set::begin.md)|Désigne le début de la séquence contrôlée.|  
|[unordered\_set::bucket](../Topic/unordered_set::bucket.md)|Obtient le numéro du compartiment pour une valeur de clé.|  
|[unordered\_set::bucket\_count](../Topic/unordered_set::bucket_count.md)|Obtient le nombre de compartiments.|  
|[unordered\_set::bucket\_size](../Topic/unordered_set::bucket_size.md)|Obtient la taille d'un compartiment.|  
|[unordered\_set::cbegin](../Topic/unordered_set::cbegin.md)|Désigne le début de la séquence contrôlée.|  
|[unordered\_set::cend](../Topic/unordered_set::cend.md)|Désigne la fin de la séquence contrôlée.|  
|[unordered\_set::clear](../Topic/unordered_set::clear.md)|Supprime tous les éléments.|  
|[unordered\_set::count](../Topic/unordered_set::count.md)|Recherche le nombre d'éléments qui correspondent à une clé spécifiée.|  
|[unordered\_set::emplace](../Topic/unordered_set::emplace.md)|Ajoute un élément construit sur place.|  
|[unordered\_set::emplace\_hint](../Topic/unordered_set::emplace_hint.md)|Ajoute un élément construit sur place, avec un indicateur.|  
|[unordered\_set::empty](../Topic/unordered_set::empty.md)|Vérifie l'absence d'éléments.|  
|[unordered\_set::end](../Topic/unordered_set::end.md)|Désigne la fin de la séquence contrôlée.|  
|[unordered\_set::equal\_range](../Topic/unordered_set::equal_range.md)|Recherche une plage qui correspond à une clé spécifiée.|  
|[unordered\_set::erase](../Topic/unordered_set::erase.md)|Supprime les éléments placés aux positions spécifiées.|  
|[unordered\_set::find](../Topic/unordered_set::find.md)|Recherche un élément qui correspond à une clé spécifiée.|  
|[unordered\_set::get\_allocator](../Topic/unordered_set::get_allocator.md)|Obtient l'objet allocateur stocké.|  
|[unordered\_set::hash\_function](../Topic/unordered_set::hash_function.md)|Obtient l'objet de fonction de hachage stocké.|  
|[unordered\_set::insert](../Topic/unordered_set::insert.md)|Ajoute des éléments.|  
|[unordered\_set::key\_eq](../Topic/unordered_set::key_eq.md)|Obtient l'objet de fonction de comparaison stocké.|  
|[unordered\_set::load\_factor](../Topic/unordered_set::load_factor.md)|Compte le nombre moyen d'éléments par compartiment.|  
|[unordered\_set::max\_bucket\_count](../Topic/unordered_set::max_bucket_count.md)|Obtient le nombre maximal de compartiments.|  
|[unordered\_set::max\_load\_factor](../Topic/unordered_set::max_load_factor.md)|Obtient ou définit le nombre maximal d'éléments par compartiment.|  
|[unordered\_set::max\_size](../Topic/unordered_set::max_size.md)|Obtient ou définit la taille maximale de la séquence contrôlée.|  
|[unordered\_set::rehash](../Topic/unordered_set::rehash.md)|Régénère la table de hachage.|  
|[unordered\_set::size](../Topic/unordered_set::size.md)|Compte le nombre d'éléments.|  
|[unordered\_set::swap](../Topic/unordered_set::swap.md)|Échange le contenu de deux conteneurs.|  
|[unordered\_set::unordered\_set](../Topic/unordered_set::unordered_set.md)|Construit un objet conteneur.|  
  
|||  
|-|-|  
|Opérateurs|Description|  
|[unordered\_set::operator\=](../Topic/unordered_set::operator=.md)|Copie une table de hachage.|  
  
## Notes  
 L'objet trie la séquence qu'il contrôle en appelant deux objets stockés, un objet de fonction de comparaison de type [unordered\_set::key\_equal](../Topic/unordered_set::key_equal.md) et un objet de fonction de hachage de type [unordered\_set::hasher](../Topic/unordered_set::hasher.md).  Pour accéder au premier objet stocké, appelez la fonction membre [unordered\_set::key\_eq](../Topic/unordered_set::key_eq.md)`()`. Pour accéder au second objet stocké, appelez la fonction membre [unordered\_set::hash\_function](../Topic/unordered_set::hash_function.md)`()`.  Pour toutes les valeurs `X` et `Y` de type `Key`, l'appel `key_eq()(X, Y)` retourne true uniquement si les valeurs des deux arguments ont un classement équivalent. L'appel `hash_function()(keyval)` génère une distribution des valeurs de type `size_t`.  Contrairement à la classe de modèle [unordered\_multiset, classe](../standard-library/unordered-multiset-class.md), un objet de classe de modèle `unordered_set` garantit que `key_eq()(X, Y)` a toujours la valeur false pour deux éléments quelconques de la séquence contrôlée. Les clés sont uniques.  
  
 L'objet stocke également un facteur de charge maximale, qui spécifie le nombre moyen maximal d'éléments souhaité par compartiment.  Si après l'insertion d'un élément, [unordered\_set::load\_factor](../Topic/unordered_set::load_factor.md)`()` dépasse le facteur de charge maximale, le conteneur augmente le nombre de compartiments et régénère la table de hachage si nécessaire.  
  
 L'ordre réel des éléments de la séquence contrôlée dépend de la fonction de hachage, de la fonction de comparaison, de l'ordre d'insertion, du facteur de charge maximale et du nombre de compartiments.  En général, il n'est pas possible de prévoir l'ordre des éléments de la séquence contrôlée.  Toutefois, vous avez la garantie que tous les sous\-ensembles d'éléments dont le classement est équivalent sont adjacents dans la séquence contrôlée.  
  
 L'objet alloue et libère du stockage pour la séquence qu'il contrôle via un objet allocateur stocké de type [unordered\_set::allocator\_type](../Topic/unordered_set::allocator_type.md).  Un tel objet allocateur doit avoir la même interface externe qu'un objet de classe de modèle `allocator`.  Notez que l'objet allocateur stocké n'est pas copié lorsque l'objet conteneur est assigné.  
  
## Configuration requise  
 **En\-tête :** \<unordered\_set\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<unordered\_set\>](../standard-library/unordered-set.md)   
 [Conteneurs](../cpp/containers-modern-cpp.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)