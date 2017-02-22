---
title: "map (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/map> (STL/CLR)"
  - "en-tête <map> (STL/CLR)"
  - "map (classe) (STL/CLR)"
ms.assetid: 8b0a7764-b5e4-4175-a802-82b72eb8662a
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# map (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes an object that controls a varying\-length sequence of elements that has bidirectional access.  You use the container `map` to manage a sequence of elements as a \(nearly\) balanced ordered tree of nodes, each storing one element.  An element consists of a key, for ordering the sequence, and a mapped value, which goes along for the ride.  
  
 In the description below, `GValue` is the same as:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 où :  
  
 `GKey` is the same as `Key` unless the latter is a ref type, in which case it is `Key^`  
  
 `GMapped` is the same as `Mapped` unless the latter is a ref type, in which case it is `Mapped^`  
  
## Syntaxe  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class map  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        System::Collections::Generic::IDictionary<Gkey, GMapped>,  
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>  
    { ..... };  
```  
  
#### Paramètres  
 Clé  
 Type du composant clé d'un élément dans la séquence contrôlée.  
  
 Mapped  
 The type of the additional component of an element in the controlled sequence.  
  
## Membres  
  
|Type Definition|Description|  
|---------------------|-----------------|  
|[map::const\_iterator](../dotnet/map-const-iterator-stl-clr.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[map::const\_reference](../dotnet/map-const-reference-stl-clr.md)|Type d'une référence constante à un élément.|  
|[map::const\_reverse\_iterator](../dotnet/map-const-reverse-iterator-stl-clr.md)|The type of a constant reverse iterator for the controlled sequence.|  
|[map::difference\_type](../dotnet/map-difference-type-stl-clr.md)|The type of a \(possibly signed\) distance between two elements.|  
|[map::generic\_container](../dotnet/map-generic-container-stl-clr.md)|The type of the generic interface for the container.|  
|[map::generic\_iterator](../dotnet/map-generic-iterator-stl-clr.md)|The type of an iterator for the generic interface for the container.|  
|[map::generic\_reverse\_iterator](../dotnet/map-generic-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the generic interface for the container.|  
|[map::generic\_value](../dotnet/map-generic-value-stl-clr.md)|The type of an element for the generic interface for the container.|  
|[map::iterator](../dotnet/map-iterator-stl-clr.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[map::key\_compare](../dotnet/map-key-compare-stl-clr.md)|The ordering delegate for two keys.|  
|[map::key\_type](../dotnet/map-key-type-stl-clr.md)|Type d'une clé de classement.|  
|[map::mapped\_type](../dotnet/map-mapped-type-stl-clr.md)|The type of the mapped value associated with each key.|  
|[map::reference](../dotnet/map-reference-stl-clr.md)|Type d'une référence à un élément.|  
|[map::reverse\_iterator](../dotnet/map-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the controlled sequence.|  
|[map::size\_type](../dotnet/map-size-type-stl-clr.md)|The type of a \(non\-negative\) distance between two elements.|  
|[map::value\_compare](../dotnet/map-value-compare-stl-clr.md)|The ordering delegate for two element values.|  
|[map::value\_type](../dotnet/map-value-type-stl-clr.md)|Le type d'un élément.|  
  
|Member Function|Description|  
|---------------------|-----------------|  
|[map::begin](../dotnet/map-begin-stl-clr.md)|Désigne le début de la séquence contrôlée.|  
|[map::clear](../dotnet/map-clear-stl-clr.md)|Removes all elements.|  
|[map::count](../dotnet/map-count-stl-clr.md)|Counts elements matching a specified key.|  
|[map::empty](../dotnet/map-empty-stl-clr.md)|Tests whether no elements are present.|  
|[map::end](../dotnet/map-end-stl-clr.md)|Désigne la fin de la séquence contrôlée.|  
|[map::equal\_range](../dotnet/map-equal-range-stl-clr.md)|Finds range that matches a specified key.|  
|[map::erase](../dotnet/map-erase-stl-clr.md)|Supprime les éléments placés aux positions spécifiées.|  
|[map::find](../dotnet/map-find-stl-clr.md)|Recherche un élément qui correspond à une clé spécifiée.|  
|[map::insert](../dotnet/map-insert-stl-clr.md)|Adds elements.|  
|[map::key\_comp](../dotnet/map-key-comp-stl-clr.md)|Copies the ordering delegate for two keys.|  
|[map::lower\_bound](../dotnet/map-lower-bound-stl-clr.md)|Finds beginning of range that matches a specified key.|  
|[map::make\_value](../dotnet/map-make-value-stl-clr.md)|Constructs a value object.|  
|[map::map](../dotnet/map-map-stl-clr.md)|Construit un objet container.|  
|[map::rbegin](../dotnet/map-rbegin-stl-clr.md)|Désigne le début de la séquence contrôlée inversée.|  
|[map::rend](../dotnet/map-rend-stl-clr.md)|Désigne la fin de la séquence contrôlée inversée.|  
|[map::size](../dotnet/map-size-stl-clr.md)|Compte le nombre d'éléments.|  
|[map::swap](../dotnet/map-swap-stl-clr.md)|Échange le contenu de deux conteneurs.|  
|[map::to\_array](../dotnet/map-to-array-stl-clr.md)|Copies the controlled sequence to a new array.|  
|[map::upper\_bound](../dotnet/map-upper-bound-stl-clr.md)|Finds end of range that matches a specified key.|  
|[map::value\_comp](../dotnet/map-value-comp-stl-clr.md)|Copies the ordering delegate for two element values.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[map::operator\=](../dotnet/map-operator-assign-stl-clr.md)|Replaces the controlled sequence.|  
|[map::operator](../dotnet/map-operator-stl-clr.md)|Maps a key to its associated mapped value.|  
|[operator\!\= \(map\)](../dotnet/operator-inequality-map-stl-clr.md)|Determines if a `map` object is not equal to another `map` object.|  
|[operator\< \(map\)](../dotnet/operator-less-than-map-stl-clr.md)|Determines if a `map` object is less than another `map` object.|  
|[operator\<\= \(map\)](../dotnet/operator-less-or-equal-map-stl-clr.md)|Determines if a `map` object is less than or equal to another `map` object.|  
|[operator\=\= \(map\)](../dotnet/operator-equality-map-stl-clr.md)|Determines if a `map` object is equal to another `map` object.|  
|[operator\> \(map\)](../dotnet/operator-greater-than-map-stl-clr.md)|Determines if a `map` object is greater than another `map` object.|  
|[operator\>\= \(map\)](../dotnet/operator-greater-or-equal-map-stl-clr.md)|Determines if a `map` object is greater than or equal to another `map` object.|  
  
## Interfaces  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Duplicate an object.|  
|<xref:System.Collections.IEnumerable>|Sequence through elements.|  
|<xref:System.Collections.ICollection>|Maintain group of elements.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Sequence through typed elements.|  
|<xref:System.Collections.Generic.ICollection%601>|Maintain group of typed elements.|  
|<xref:System.Collections.Generic.IDictionary%602>|Maintain group of {key, value} pairs.|  
|ITree\<Key, Value\>|Maintain generic container.|  
  
## Notes  
 The object allocates and frees storage for the sequence it controls as individual nodes.  It inserts elements into a \(nearly\) balanced tree that it keeps ordered by altering the links between nodes, never by copying the contents of one node to another.  That means you can insert and remove elements freely without disturbing remaining elements.  
  
 The object orders the sequence it controls by calling a stored delegate object of type [map::key\_compare](../dotnet/map-key-compare-stl-clr.md).  You can specify the stored delegate object when you construct the map; if you specify no delegate object, the default is the comparison `operator<(key_type, key_type)`.  You access this stored object by calling the member function [map::key\_comp](../dotnet/map-key-comp-stl-clr.md)`()`.  
  
 Such a delegate object must impose a strict weak ordering on keys of type [map::key\_type](../dotnet/map-key-type-stl-clr.md).  That means, for any two keys `X` and `Y`:  
  
 `key_comp()(X, Y)` returns the same Boolean result on every call.  
  
 If `key_comp()(X, Y)` is true, then `key_comp()(Y, X)` must be false.  
  
 If `key_comp()(X, Y)` is true, then `X` is said to be ordered before `Y`.  
  
 If `!key_comp()(X, Y) && !key_comp()(Y, X)` is true, then `X` and `Y` are said to have equivalent ordering.  
  
 For any element `X` that precedes `Y` in the controlled sequence, `key_comp()(Y, X)` is false. \(For the default delegate object, keys never decrease in value.\) Unlike template class [map](../dotnet/map-stl-clr.md), an object of template class `map` does not require that keys for all elements are unique. \(Two or more keys can have equivalent ordering.\)  
  
 Each element contains a separate key and a mapped value.  The sequence is represented in a way that permits lookup, insertion, and removal of an arbitrary element with a number of operations proportional to the logarithm of the number of elements in the sequence \(logarithmic time\).  Moreover, inserting an element invalidates no iterators, and removing an element invalidates only those iterators which point at the removed element.  
  
 A map supports bidirectional iterators, which means you can step to adjacent elements given an iterator that designates an element in the controlled sequence.  A special head node corresponds to the iterator returned by [map::end](../dotnet/map-end-stl-clr.md)`()`.  You can decrement this iterator to reach the last element in the controlled sequence, if present.  You can increment a map iterator to reach the head node, and it will then compare equal to `end()`.  But you cannot dereference the iterator returned by `end()`.  
  
 Note that you cannot refer to a map element directly given its numerical position \-\- that requires a random\-access iterator.  
  
 A map iterator stores a handle to its associated map node, which in turn stores a handle to its associated container.  You can use iterators only with their associated container objects.  A map iterator remains valid so long as its associated map node is associated with some map.  Moreover, a valid iterator is dereferencable \-\- you can use it to access or alter the element value it designates \-\- so long as it is not equal to `end()`.  
  
 Erasing or removing an element calls the destructor for its stored value.  Destroying the container erases all elements.  Thus, a container whose element type is a ref class ensures that no elements outlive the container.  Note, however, that a container of handles does `not` destroy its elements.  
  
## Configuration requise  
 **Header:** \<cliext\/map\>  
  
 **Namespace:** cliext  
  
## Voir aussi  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)