---
title: "deque (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/deque> [STL/CLR]"
  - "en-tête <deque> [STL/CLR]"
  - "classe deque [STL/CLR]"
ms.assetid: dd669da3-3c0e-45e9-8596-f6b483720941
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# deque (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes an object that controls a varying\-length sequence of elements that has random access.  You use the container `deque` to manage a sequence of elements that looks like a contiguous block of storage, but which can grow or shrink at either end without the need to copy any remaining elements.  Thus it can implement efficiently a `double-ended queue`. \(Hence the name.\)  
  
 In the description below, `GValue` is the same as `Value` unless the latter is a ref type, in which case it is `Value^`.  
  
## Syntaxe  
  
```  
template<typename Value>  
    ref class deque  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IDeque<GValue>  
    { ..... };  
```  
  
#### Paramètres  
 GValue  
 The generic type of an element in the controlled sequence.  
  
 Valeur  
 Type d'un élément dans la séquence contrôlée.  
  
## Membres  
  
|Type Definition|Description|  
|---------------------|-----------------|  
|[deque::const\_iterator](../dotnet/deque-const-iterator-stl-clr.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[deque::const\_reference](../dotnet/deque-const-reference-stl-clr.md)|Type d'une référence constante à un élément.|  
|[deque::const\_reverse\_iterator](../dotnet/deque-const-reverse-iterator-stl-clr.md)|The type of a constant reverse iterator for the controlled sequence.|  
|[deque::difference\_type](../dotnet/deque-difference-type-stl-clr.md)|Type d'une distance signée entre deux éléments.|  
|[deque::generic\_container](../dotnet/deque-generic-container-stl-clr.md)|The type of the generic interface for the container.|  
|[deque::generic\_iterator](../dotnet/deque-generic-iterator-stl-clr.md)|The type of an iterator for the generic interface for the container.|  
|[deque::generic\_reverse\_iterator](../dotnet/deque-generic-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the generic interface for the container.|  
|[deque::generic\_value](../dotnet/deque-generic-value-stl-clr.md)|The type of an element for the generic interface for the container.|  
|[deque::iterator](../dotnet/deque-iterator-stl-clr.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[deque::reference](../dotnet/deque-reference-stl-clr.md)|Type d'une référence à un élément.|  
|[deque::reverse\_iterator](../dotnet/deque-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the controlled sequence.|  
|[deque::size\_type](../dotnet/deque-size-type-stl-clr.md)|Type d'une distance signée entre deux éléments.|  
|[deque::value\_type](../dotnet/deque-value-type-stl-clr.md)|Le type d'un élément.|  
  
|Member Function|Description|  
|---------------------|-----------------|  
|[deque::assign](../dotnet/deque-assign-stl-clr.md)|Replaces all elements.|  
|[deque::at](../dotnet/deque-at-stl-clr.md)|Accesses an element at a specified position.|  
|[deque::back](../dotnet/deque-back-stl-clr.md)|Accesses the last element.|  
|[deque::begin](../dotnet/deque-begin-stl-clr.md)|Désigne le début de la séquence contrôlée.|  
|[deque::clear](../dotnet/deque-clear-stl-clr.md)|Removes all elements.|  
|[deque::deque](../dotnet/deque-deque-stl-clr.md)|Construit un objet container.|  
|[deque::empty](../dotnet/deque-empty-stl-clr.md)|Tests whether no elements are present.|  
|[deque::end](../dotnet/deque-end-stl-clr.md)|Désigne la fin de la séquence contrôlée.|  
|[deque::erase](../dotnet/deque-erase-stl-clr.md)|Supprime les éléments placés aux positions spécifiées.|  
|[deque::front](../dotnet/deque-front-stl-clr.md)|Accesses the first element.|  
|[deque::insert](../dotnet/deque-insert-stl-clr.md)|Adds elements at a specified position.|  
|[deque::pop\_back](../dotnet/deque-pop-back-stl-clr.md)|Removes the last element.|  
|[deque::pop\_front](../dotnet/deque-pop-front-stl-clr.md)|Removes the first element.|  
|[deque::push\_back](../dotnet/deque-push-back-stl-clr.md)|Adds a new last element.|  
|[deque::push\_front](../dotnet/deque-push-front-stl-clr.md)|Adds a new first element.|  
|[deque::rbegin](../dotnet/deque-rbegin-stl-clr.md)|Désigne le début de la séquence contrôlée inversée.|  
|[deque::rend](../dotnet/deque-rend-stl-clr.md)|Désigne la fin de la séquence contrôlée inversée.|  
|[deque::resize](../dotnet/deque-resize-stl-clr.md)|Change le nombre d'éléments.|  
|[deque::size](../dotnet/deque-size-stl-clr.md)|Compte le nombre d'éléments.|  
|[deque::swap](../dotnet/deque-swap-stl-clr.md)|Échange le contenu de deux conteneurs.|  
|[deque::to\_array](../dotnet/deque-to-array-stl-clr.md)|Copies the controlled sequence to a new array.|  
  
|Propriété|Description|  
|---------------|-----------------|  
|[deque::back\_item](../dotnet/deque-back-item-stl-clr.md)|Accesses the last element.|  
|[deque::front\_item](../dotnet/deque-front-item-stl-clr.md)|Accesses the first element.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[deque::operator\!\=](../dotnet/deque-operator-inequality-stl-clr.md)|Détermine si deux objets `deque` ne sont pas égaux.|  
|[deque::operator](../dotnet/deque-operator-stl-clr.md)|Accesses an element at a specified position.|  
|[operator\< \(deque\)](../dotnet/operator-less-than-deque-stl-clr.md)|Determines if a `deque` object is less than another `deque` object.|  
|[operator\<\= \(deque\)](../dotnet/operator-less-or-equal-deque-stl-clr.md)|Determines if a `deque` object is less than or equal to another `deque` object.|  
|[operator\= \(deque\)](../dotnet/operator-assign-deque-stl-clr.md)|Replaces the controlled sequence.|  
|[operator\=\= \(deque\)](../dotnet/operator-equality-deque-stl-clr.md)|Determines if a `deque` object is equal to another `deque` object.|  
|[operator\> \(deque\)](../dotnet/operator-greater-than-deque-stl-clr.md)|Determines if a `deque` object is greater than another `deque` object.|  
|[operator\>\= \(deque\)](../dotnet/operator-greater-or-equal-deque-stl-clr.md)|Determines if a `deque` object is greater than or equal to another `deque` object.|  
  
## Interfaces  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Duplicate an object.|  
|<xref:System.Collections.IEnumerable>|Sequence through elements.|  
|<xref:System.Collections.ICollection>|Maintain group of elements.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Sequence through typed elements.|  
|<xref:System.Collections.Generic.ICollection%601>|Maintain group of typed elements.|  
|<xref:System.Collections.Generic.IList%601>|Maintain ordered group of typed elements.|  
|IDeque\<Value\>|Maintain generic container.|  
  
## Notes  
 The object allocates and frees storage for the sequence it controls through a stored array of handles that designate blocks of `Value` elements.  The array grows on demand.  Growth occurs in such a way that the cost of either prepending or appending a new element is constant time, and no remaining elements are disturbed.  You can also remove an element at either end in constant time, and without disturbing remaining elements.  Thus, a deque is a good candidate for the underlying container for template class [queue](../dotnet/queue-stl-clr.md) or template class [pile](../dotnet/stack-stl-clr.md).  
  
 A `deque` object supports random\-access iterators, which means you can refer to an element directly given its numerical position, counting from zero for the first \(front\) element, to [deque::size](../dotnet/deque-size-stl-clr.md)`() - 1` for the last \(back\) element.  It also means that a deque is a good candidate for the underlying container for template class [priority\_queue](../dotnet/priority-queue-stl-clr.md).  
  
 A deque iterator stores a handle to its associated deque object, along with the bias of the element it designates.  You can use iterators only with their associated container objects.  The bias of a deque element is `not` necessarily the same as its position.  The first element inserted has bias zero, the next appended element has bias 1, but the next prepended element has bias \-1.  
  
 Inserting or erasing elements at either end does `not` alter the value of an element stored at any valid bias.  Inserting or erasing an interior element, however, `can` change the element value stored at a given bias, so the value designated by an iterator can also change. \(The container may have to copy elements up or down to create a hole before an insert or to fill a hole after an erase.\) Nevertheless, a deque iterator remains valid so long as its bias designates a valid element.  Moreover, a valid iterator remains dereferencable \-\- you can use it to access or alter the element value it designates \-\- so long as its bias is not equal to the bias for the iterator returned by `end()`.  
  
 Erasing or removing an element calls the destructor for its stored value.  Destroying the container erases all elements.  Thus, a container whose element type is a ref class ensures that no elements outlive the container.  Note, however, that a container of handles does `not` destroy its elements.  
  
## Configuration requise  
 **Header:** \<cliext\/deque\>  
  
 **Namespace:** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)   
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [queue](../dotnet/queue-stl-clr.md)   
 [pile](../dotnet/stack-stl-clr.md)   
 [vecteur](../dotnet/vector-stl-clr.md)   
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)