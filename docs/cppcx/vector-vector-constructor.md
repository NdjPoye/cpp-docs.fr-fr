---
title: "Vector::Vector (constructeur) | Microsoft Docs"
ms.custom: ""
ms.date: "01/24/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::Vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::Vector (constructeur)"
ms.assetid: 5454433d-e206-45ea-bc8b-bb5a7bf38c17
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::Vector (constructeur)
Initialise une nouvelle instance de la classe Vector.  
  
## Syntaxe  
  
```  
Vector();  
  
explicit Vector(  
    unsigned int size  
    );  
  
Vector(  
    unsigned int size,  
    T value  
    );  
  
template <typename U> explicit Vector(  
    const ::std::vector<U>& v  
    );  
  
template <typename U> explicit Vector(  
    std::vector<U>&& v  
    );  
  
Vector(  
    const T * ptr,  
    unsigned int size  
    );  
  
template <size_t N> explicit Vector(  
    const T(&arr)[N]  
    );  
  
template <size_t N> explicit Vector(  
    const std::array<T, N>& a  
    );  
  
explicit Vector(  
    const Array<T>^ arr  
    );  
  
template <typename InIt> Vector(  
    InIt first,  
    InIt last  
    );  
  
Vector(  
    std::initializer_list<T> il  
    );  
```  
  
#### Paramètres  
 a  
 Objet [std::array](../standard-library/array-class-stl.md) qui sera utilisé pour initialiser le Vector.  
  
 a  
 Objet [Platform::Array](../cppcx/platform-array-class.md) qui sera utilisé pour initialiser le Vector.  
  
 `InIt`  
 Type d'une collection d'objets utilisée pour initialiser l'objet Vector actuel.  
  
 il  
 [std::initializer\_list](../standard-library/initializer-list-class.md) des objets de type `T` qui seront utilisés pour initialiser le Vector.  
  
 `N`  
 Nombre d'éléments d'une collection d'objets utilisée pour initialiser l'objet Vector actuel.  
  
 `size`  
 Nombre d'éléments dans l'objet Vector.  
  
 `value`  
 Valeur utilisée pour initialiser chaque élément de l'objet Vector actuel.  
  
 `v`  
 [Lvalues et Rvalues](../Topic/Lvalues%20and%20Rvalues%20\(Visual%20C++\).md) à un [std::vector](../Topic/vector%20Class%201.md) utilisé pour initialiser l'objet Vector actuel.  
  
 `ptr`  
 Pointeur vers un `std::vector` utilisé pour initialiser l'objet Vector actuel.  
  
 `arr`  
 Objet [Platform::Array](../cppcx/platform-array-class.md) utilisé pour initialiser l'objet Vector actuel.  
  
 `a`  
 Objet [std::array](../Topic/vector%20Class%201.md) utilisé pour initialiser l'objet Vector actuel.  
  
 `first`  
 Premier élément d'une séquence d'objets utilisée pour initialiser l'objet Vector actuel. Le type `first` est passé au moyen du *transfert parfait*. Pour plus d'informations, consultez [Déclarateur de référence Rvalue : &&](../Topic/Rvalue%20Reference%20Declarator:%20&&.md).  
  
 `last`  
 Dernier élément d'une séquence d'objets utilisée pour initialiser l'objet Vector actuel. Le type `last` est passé au moyen du *transfert parfait*. Pour plus d'informations, consultez [Déclarateur de référence Rvalue : &&](../Topic/Rvalue%20Reference%20Declarator:%20&&.md).  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::Vector, classe](../cppcx/platform-collections-vector-class.md)   
 [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)