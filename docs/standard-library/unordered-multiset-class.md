---
title: "unordered_multiset, classe | Microsoft Docs"
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
  - "tr1::unordered_multiset"
  - "std::tr1::unordered_multiset"
  - "unordered_multiset"
  - "std.tr1.unordered_multiset"
  - "unordered_set/std::tr1::unordered_multiset"
  - "tr1.unordered_multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unordered_multiset (classe)"
  - "unordered_multiset (classe) (TR1)"
ms.assetid: 70c8dfc5-492a-4af2-84f5-1aa9cb04b71c
caps.latest.revision: 24
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# unordered_multiset, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle décrit un objet qui contrôle une séquence de longueur variable constituée d'éléments de type `const Key`.  La séquence est triée par ordre faible avec une fonction de hachage, qui partitionne la séquence en un ensemble trié de sous\-séquences appelées compartiments.  Dans chaque compartiment, une fonction de comparaison détermine si des paires d'éléments possèdent un ordre équivalent.  Chaque élément sert à la fois de clé de tri et de valeur.  La séquence est représentée de façon à permettre la recherche, l'insertion et la suppression d'un élément arbitraire à l'aide d'un certain nombre d'opérations qui peut être indépendant du nombre d'éléments de la séquence \(temps constant\), du moins lorsque les compartiments sont de longueur à peu près équivalente.  Dans le pire des cas, lorsque tous les éléments se trouvent dans un compartiment, le nombre d'opérations est proportionnel au nombre d'éléments de la séquence \(temps linéaire\).  De plus, l'insertion d'un élément n'entraîne pas la non validité des itérateurs, et la suppression d'un élément ne rend non valides que les itérateurs qui pointent vers l'élément supprimé.  
  
## Syntaxe  
  
```  
template<class Key,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<Key> >  
    class unordered_multiset;  
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
|[unordered\_multiset::allocator\_type](../Topic/unordered_multiset::allocator_type.md)|Type d'un allocateur pour la gestion du stockage.|  
|[unordered\_multiset::const\_iterator](../Topic/unordered_multiset::const_iterator.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[unordered\_multiset::const\_local\_iterator](../Topic/unordered_multiset::const_local_iterator.md)|Type d'un itérateur de compartiment constant pour la séquence contrôlée.|  
|[unordered\_multiset::const\_pointer](../Topic/unordered_multiset::const_pointer.md)|Type d'un pointeur constant vers un élément.|  
|[unordered\_multiset::const\_reference](../Topic/unordered_multiset::const_reference.md)|Type d'une référence constante à un élément.|  
|[unordered\_multiset::difference\_type](../Topic/unordered_multiset::difference_type.md)|Type d'une distance signée entre deux éléments.|  
|[unordered\_multiset::hasher](../Topic/unordered_multiset::hasher.md)|Type de la fonction de hachage.|  
|[unordered\_multiset::iterator](../Topic/unordered_multiset::iterator.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[unordered\_multiset::key\_equal](../Topic/unordered_multiset::key_equal.md)|Type de la fonction de comparaison.|  
|[unordered\_multiset::key\_type](../Topic/unordered_multiset::key_type.md)|Type d'une clé de tri.|  
|[unordered\_multiset::local\_iterator](../Topic/unordered_multiset::local_iterator.md)|Type d'un itérateur de compartiment pour la séquence contrôlée.|  
|[unordered\_multiset::pointer](../Topic/unordered_multiset::pointer.md)|Type d'un pointeur vers un élément.|  
|[unordered\_multiset::reference](../Topic/unordered_multiset::reference.md)|Type d'une référence à un élément.|  
|[unordered\_multiset::size\_type](../Topic/unordered_multiset::size_type.md)|Type d'une distance non signée entre deux éléments.|  
|[unordered\_multiset::value\_type](../Topic/unordered_multiset::value_type.md)|Type d'un élément.|  
  
|||  
|-|-|  
|Fonction membre|Description|  
|[unordered\_multiset::begin](../Topic/unordered_multiset::begin.md)|Désigne le début de la séquence contrôlée.|  
|[unordered\_multiset::bucket](../Topic/unordered_multiset::bucket.md)|Obtient le numéro du compartiment pour une valeur de clé.|  
|[unordered\_multiset::bucket\_count](../Topic/unordered_multiset::bucket_count.md)|Obtient le nombre de compartiments.|  
|[unordered\_multiset::bucket\_size](../Topic/unordered_multiset::bucket_size.md)|Obtient la taille d'un compartiment.|  
|[unordered\_multiset::cbegin](../Topic/unordered_multiset::cbegin.md)|Désigne le début de la séquence contrôlée.|  
|[unordered\_multiset::cend](../Topic/unordered_multiset::cend.md)|Désigne la fin de la séquence contrôlée.|  
|[unordered\_multiset::clear](../Topic/unordered_multiset::clear.md)|Supprime tous les éléments.|  
|[unordered\_multiset::count](../Topic/unordered_multiset::count.md)|Recherche le nombre d'éléments qui correspondent à une clé spécifiée.|  
|[unordered\_multiset::emplace](../Topic/unordered_multiset::emplace.md)|Ajoute un élément construit sur place.|  
|[unordered\_multiset::emplace\_hint](../Topic/unordered_multiset::emplace_hint.md)|Ajoute un élément construit sur place, avec un indicateur.|  
|[unordered\_multiset::empty](../Topic/unordered_multiset::empty.md)|Vérifie l'absence d'éléments.|  
|[unordered\_multiset::end](../Topic/unordered_multiset::end.md)|Désigne la fin de la séquence contrôlée.|  
|[unordered\_multiset::equal\_range](../Topic/unordered_multiset::equal_range.md)|Recherche une plage qui correspond à une clé spécifiée.|  
|[unordered\_multiset::erase](../Topic/unordered_multiset::erase.md)|Supprime les éléments placés aux positions spécifiées.|  
|[unordered\_multiset::find](../Topic/unordered_multiset::find.md)|Recherche un élément qui correspond à une clé spécifiée.|  
|[unordered\_multiset::get\_allocator](../Topic/unordered_multiset::get_allocator.md)|Obtient l'objet allocateur stocké.|  
|[unordered\_multiset::hash\_function](../Topic/unordered_multiset::hash_function.md)|Obtient l'objet de fonction de hachage stocké.|  
|[unordered\_multiset::insert](../Topic/unordered_multiset::insert.md)|Ajoute des éléments.|  
|[unordered\_multiset::key\_eq](../Topic/unordered_multiset::key_eq.md)|Obtient l'objet de fonction de comparaison stocké.|  
|[unordered\_multiset::load\_factor](../Topic/unordered_multiset::load_factor.md)|Compte le nombre moyen d'éléments par compartiment.|  
|[unordered\_multiset::max\_bucket\_count](../Topic/unordered_multiset::max_bucket_count.md)|Obtient le nombre maximal de compartiments.|  
|[unordered\_multiset::max\_load\_factor](../Topic/unordered_multiset::max_load_factor.md)|Obtient ou définit le nombre maximal d'éléments par compartiment.|  
|[unordered\_multiset::max\_size](../Topic/unordered_multiset::max_size.md)|Obtient ou définit la taille maximale de la séquence contrôlée.|  
|[unordered\_multiset::rehash](../Topic/unordered_multiset::rehash.md)|Régénère la table de hachage.|  
|[unordered\_multiset::size](../Topic/unordered_multiset::size.md)|Compte le nombre d'éléments.|  
|[unordered\_multiset::swap](../Topic/unordered_multiset::swap.md)|Échange le contenu de deux conteneurs.|  
|[unordered\_multiset::unordered\_multiset](../Topic/unordered_multiset::unordered_multiset.md)|Construit un objet conteneur.|  
  
|||  
|-|-|  
|Opérateur|Description|  
|[unordered\_multiset::operator\=](../Topic/unordered_multiset::operator=.md)|Copie une table de hachage.|  
  
## Notes  
 L'objet trie la séquence qu'il contrôle en appelant deux objets stockés, un objet de fonction de comparaison de type [unordered\_multiset::key\_equal](../Topic/unordered_multiset::key_equal.md) et un objet de fonction de hachage de type [unordered\_multiset::hasher](../Topic/unordered_multiset::hasher.md).  Pour accéder au premier objet stocké, appelez la fonction membre [unordered\_multiset::key\_eq](../Topic/unordered_multiset::key_eq.md)`()`. Pour accéder au second objet stocké, appelez la fonction membre [unordered\_multiset::hash\_function](../Topic/unordered_multiset::hash_function.md)`()`.  Pour toutes les valeurs `X` et `Y` de type `Key`, l'appel `key_eq()(X, Y)` retourne true uniquement si les valeurs des deux arguments ont un classement équivalent. L'appel `hash_function()(keyval)` génère une distribution des valeurs de type `size_t`.  Contrairement à la classe de modèle [unordered\_set, classe](../standard-library/unordered-set-class.md), un objet de classe de modèle `unordered_multiset` ne garantit pas que `key_eq()(X, Y)` est toujours false pour deux des éléments de la séquence contrôlée. Il n'est pas nécessaire que les clés soient uniques.  
  
 L'objet stocke également un facteur de charge maximale, qui spécifie le nombre moyen maximal d'éléments souhaité par compartiment.  Si après l'insertion d'un élément, [unordered\_multiset::load\_factor](../Topic/unordered_multiset::load_factor.md)`()` dépasse le facteur de charge maximale, le conteneur augmente le nombre de compartiments et régénère la table de hachage si nécessaire.  
  
 L'ordre réel des éléments de la séquence contrôlée dépend de la fonction de hachage, de la fonction de comparaison, de l'ordre d'insertion, du facteur de charge maximale et du nombre de compartiments.  En général, il n'est pas possible de prévoir l'ordre des éléments de la séquence contrôlée.  Toutefois, vous avez la garantie que tous les sous\-ensembles d'éléments dont le classement est équivalent sont adjacents dans la séquence contrôlée.  
  
 L'objet alloue et libère du stockage pour la séquence qu'il contrôle via un objet allocateur stocké de type [unordered\_multiset::allocator\_type](../Topic/unordered_multiset::allocator_type.md).  Un tel objet allocateur doit avoir la même interface externe qu'un objet de classe de modèle `allocator`.  Notez que l'objet allocateur stocké n'est pas copié lorsque l'objet conteneur est assigné.  
  
## Configuration requise  
 **En\-tête :** \<unordered\_set\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<unordered\_set\>](../standard-library/unordered-set.md)   
 [Conteneurs](../cpp/containers-modern-cpp.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)