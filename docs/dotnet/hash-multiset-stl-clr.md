---
title: "hash_multiset (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/hash_set> [STL/CLR]"
  - "en-tête <hash_set> [STL/CLR]"
  - "classe hash_multiset [STL/CLR]"
ms.assetid: 8462bd21-6829-4dd3-ac81-c42d6fdf92f0
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# hash_multiset (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes an object that controls a varying\-length sequence of elements that has bidirectional access.  You use the container `hash_multiset` to manage a sequence of elements as a hash table, each table entry storing a bidirectional linked list of nodes, and each node storing one element.  The value of each element is used as a key, for ordering the sequence.  
  
 In the description below, `GValue` is the same as `GKey`, which in turn is the same as `Key` unless the latter is a ref type, in which case it is `Key^`.  
  
## Syntaxe  
  
```  
template<typename Key>  
    ref class hash_multiset  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>  
    { ..... };  
```  
  
#### Paramètres  
 Clé  
 Type du composant clé d'un élément dans la séquence contrôlée.  
  
## Membres  
  
|Type Definition|Description|  
|---------------------|-----------------|  
|[hash\_multiset::const\_iterator](../dotnet/hash-multiset-const-iterator-stl-clr.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[hash\_multiset::const\_reference](../dotnet/hash-multiset-const-reference-stl-clr.md)|Type d'une référence constante à un élément.|  
|[hash\_multiset::const\_reverse\_iterator](../dotnet/hash-multiset-const-reverse-iterator-stl-clr.md)|The type of a constant reverse iterator for the controlled sequence.|  
|[hash\_multiset::difference\_type](../dotnet/hash-multiset-difference-type-stl-clr.md)|The type of a \(possibly signed\) distance between two elements.|  
|[hash\_multiset::generic\_container](../dotnet/hash-multiset-generic-container-stl-clr.md)|The type of the generic interface for the container.|  
|[hash\_multiset::generic\_iterator](../dotnet/hash-multiset-generic-iterator-stl-clr.md)|The type of an iterator for the generic interface for the container.|  
|[hash\_multiset::generic\_reverse\_iterator](../dotnet/hash-multiset-generic-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the generic interface for the container.|  
|[hash\_multiset::generic\_value](../dotnet/hash-multiset-generic-value-stl-clr.md)|The type of an element for the generic interface for the container.|  
|[hash\_multiset::hasher](../dotnet/hash-multiset-hasher-stl-clr.md)|The hashing delegate for a key.|  
|[hash\_multiset::iterator](../dotnet/hash-multiset-iterator-stl-clr.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[hash\_multiset::key\_compare](../dotnet/hash-multiset-key-compare-stl-clr.md)|The ordering delegate for two keys.|  
|[hash\_multiset::key\_type](../dotnet/hash-multiset-key-type-stl-clr.md)|Type d'une clé de classement.|  
|[hash\_multiset::reference](../dotnet/hash-multiset-reference-stl-clr.md)|Type d'une référence à un élément.|  
|[hash\_multiset::reverse\_iterator](../dotnet/hash-multiset-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the controlled sequence.|  
|[hash\_multiset::size\_type](../dotnet/hash-multiset-size-type-stl-clr.md)|The type of a \(non\-negative\) distance between two elements.|  
|[hash\_multiset::value\_compare](../dotnet/hash-multiset-value-compare-stl-clr.md)|The ordering delegate for two element values.|  
|[hash\_multiset::value\_type](../dotnet/hash-multiset-value-type-stl-clr.md)|Le type d'un élément.|  
  
|Member Function|Description|  
|---------------------|-----------------|  
|[hash\_multiset::begin](../dotnet/hash-multiset-begin-stl-clr.md)|Désigne le début de la séquence contrôlée.|  
|[hash\_multiset::bucket\_count](../dotnet/hash-multiset-bucket-count-stl-clr.md)|Counts the number of buckets.|  
|[hash\_multiset::clear](../dotnet/hash-multiset-clear-stl-clr.md)|Removes all elements.|  
|[hash\_multiset::count](../dotnet/hash-multiset-count-stl-clr.md)|Counts elements matching a specified key.|  
|[hash\_multiset::empty](../dotnet/hash-multiset-empty-stl-clr.md)|Tests whether no elements are present.|  
|[hash\_multiset::end](../dotnet/hash-multiset-end-stl-clr.md)|Désigne la fin de la séquence contrôlée.|  
|[hash\_multiset::equal\_range](../dotnet/hash-multiset-equal-range-stl-clr.md)|Finds range that matches a specified key.|  
|[hash\_multiset::erase](../dotnet/hash-multiset-erase-stl-clr.md)|Supprime les éléments placés aux positions spécifiées.|  
|[hash\_multiset::find](../dotnet/hash-multiset-find-stl-clr.md)|Recherche un élément qui correspond à une clé spécifiée.|  
|[hash\_multiset::hash\_delegate](../dotnet/hash-multiset-hash-delegate-stl-clr.md)|Copies the hashing delegate for a key.|  
|[hash\_multiset::hash\_multiset](../dotnet/hash-multiset-hash-multiset-stl-clr.md)|Construit un objet container.|  
|[hash\_multiset::insert](../dotnet/hash-multiset-insert-stl-clr.md)|Adds elements.|  
|[hash\_multiset::key\_comp](../dotnet/hash-multiset-key-comp-stl-clr.md)|Copies the ordering delegate for two keys.|  
|[hash\_multiset::load\_factor](../dotnet/hash-multiset-load-factor-stl-clr.md)|Counts the average elements per bucket.|  
|[hash\_multiset::lower\_bound](../dotnet/hash-multiset-lower-bound-stl-clr.md)|Finds beginning of range that matches a specified key.|  
|[hash\_multiset::make\_value](../dotnet/hash-multiset-make-value-stl-clr.md)|Constructs a value object.|  
|[hash\_multiset::max\_load\_factor](../dotnet/hash-multiset-max-load-factor-stl-clr.md)|Gets or sets the maximum elements per bucket.|  
|[hash\_multiset::rbegin](../dotnet/hash-multiset-rbegin-stl-clr.md)|Désigne le début de la séquence contrôlée inversée.|  
|[hash\_multiset::rehash](../dotnet/hash-multiset-rehash-stl-clr.md)|Régénère la table de hachage.|  
|[hash\_multiset::rend](../dotnet/hash-multiset-rend-stl-clr.md)|Désigne la fin de la séquence contrôlée inversée.|  
|[hash\_multiset::size](../dotnet/hash-multiset-size-stl-clr.md)|Compte le nombre d'éléments.|  
|[hash\_multiset::swap](../dotnet/hash-multiset-swap-stl-clr.md)|Échange le contenu de deux conteneurs.|  
|[hash\_multiset::to\_array](../dotnet/hash-multiset-to-array-stl-clr.md)|Copies the controlled sequence to a new array.|  
|[hash\_multiset::upper\_bound](../dotnet/hash-multiset-upper-bound-stl-clr.md)|Finds end of range that matches a specified key.|  
|[hash\_multiset::value\_comp](../dotnet/hash-multiset-value-comp-stl-clr.md)|Copies the ordering delegate for two element values.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[hash\_multiset::operator\=](../dotnet/hash-multiset-operator-assign-stl-clr.md)|Replaces the controlled sequence.|  
  
## Interfaces  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Duplicate an object.|  
|<xref:System.Collections.IEnumerable>|Sequence through elements.|  
|<xref:System.Collections.ICollection>|Maintain group of elements.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Sequence through typed elements.|  
|<xref:System.Collections.Generic.ICollection%601>|Maintain group of typed elements.|  
|IHash\<Key, Value\>|Maintain generic container.|  
  
## Notes  
 The object allocates and frees storage for the sequence it controls as individual nodes in a bidirectional linked list.  To speed access, the object also maintains a varying\-length array of pointers into the list \(the hash table\), effectively managing the whole list as a sequence of sublists, or buckets.  It inserts elements into a bucket that it keeps ordered by altering the links between nodes, never by copying the contents of one node to another.  That means you can insert and remove elements freely without disturbing remaining elements.  
  
 The object orders each bucket it controls by calling a stored delegate object of type [hash\_set::key\_compare](../dotnet/hash-set-key-compare-stl-clr.md).  You can specify the stored delegate object when you construct the hash\_set; if you specify no delegate object, the default is the comparison `operator<=(key_type, key_type)`.  
  
 You access the stored delegate object by calling the member function [hash\_set::key\_comp](../dotnet/hash-set-key-comp-stl-clr.md)`()`.  Such a delegate object must define equivalent ordering between keys of type [hash\_set::key\_type](../dotnet/hash-set-key-type-stl-clr.md).  That means, for any two keys `X` and `Y`:  
  
 `key_comp()(X, Y)` returns the same Boolean result on every call.  
  
 If `key_comp()(X, Y) && key_comp()(Y, X)` is true, then `X` and `Y` are said to have equivalent ordering.  
  
 Any ordering rule that behaves like `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` or `operator==(key_type, key_type)` defines eqivalent ordering.  
  
 Note that the container ensures only that elements whose keys have equivalent ordering \(and which hash to the same integer value\) are adjacent within a bucket.  Unlike template class [hash\_set](../dotnet/hash-set-stl-clr.md), an object of template class `hash_multiset` does not require that keys for all elements are unique. \(Two or more keys can have equivalent ordering.\)  
  
 The object determines which bucket should contain a given ordering key by calling a stored delegate object of type [hash\_set::hasher](../dotnet/hash-set-hasher-stl-clr.md).  You access this stored object by calling the member function [hash\_set::hash\_delegate](../dotnet/hash-set-hash-delegate-stl-clr.md)`()` to obtain an integer value that depends on the key value.  You can specify the stored delegate object when you construct the hash\_set; if you specify no delegate object, the default is the function `System::Object::hash_value(key_type)`.  That means, for any keys `X` and `Y`:  
  
 `hash_delegate()(X)` returns the same integer result on every call.  
  
 If `X` and `Y` have equivalent ordering, then `hash_delegate()(X)` should return the same integer result as `hash_delegate()(Y)`.  
  
 Each element serves as both a key and a value.  The sequence is represented in a way that permits lookup, insertion, and removal of an arbitrary element with a number of operations that is independent of the number of elements in the sequence \(constant time\) \-\- at least in the best of cases.  Moreover, inserting an element invalidates no iterators, and removing an element invalidates only those iterators which point at the removed element.  
  
 If hashed values are not uniformly distributed, however, a hash table can degenerate.  In the extreme \-\- for a hash function that always returns the same value \-\- lookup, insertion, and removal are proportional to the number of elements in the sequence \(linear time\).  The container endeavors to choose a reasonable hash function, mean bucket size, and hash\-table size \(total number of buckets\), but you can override any or all of these choices.  See, for example, the functions [hash\_set::max\_load\_factor](../dotnet/hash-set-max-load-factor-stl-clr.md) and [hash\_set::rehash](../dotnet/hash-set-rehash-stl-clr.md).  
  
 A hash\_multiset supports bidirectional iterators, which means you can step to adjacent elements given an iterator that designates an element in the controlled sequence.  A special head node corresponds to the iterator returned by [hash\_multiset::end](../dotnet/hash-multiset-end-stl-clr.md)`()`.  You can decrement this iterator to reach the last element in the controlled sequence, if present.  You can increment a hash\_multiset iterator to reach the head node, and it will then compare equal to `end()`.  But you cannot dereference the iterator returned by `end()`.  
  
 Note that you cannot refer to a hash\_multiset element directly given its numerical position \-\- that requires a random\-access iterator.  
  
 A hash\_multiset iterator stores a handle to its associated hash\_multiset node, which in turn stores a handle to its associated container.  You can use iterators only with their associated container objects.  A hash\_multiset iterator remains valid so long as its associated hash\_multiset node is associated with some hash\_multiset.  Moreover, a valid iterator is dereferencable \-\- you can use it to access or alter the element value it designates \-\- so long as it is not equal to `end()`.  
  
 Erasing or removing an element calls the destructor for its stored value.  Destroying the container erases all elements.  Thus, a container whose element type is a ref class ensures that no elements outlive the container.  Note, however, that a container of handles does `not` destroy its elements.  
  
## Configuration requise  
 **Header:** \<cliext\/hash\_set\>  
  
 **Namespace:** cliext  
  
## Voir aussi  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)