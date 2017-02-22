---
title: "Allocateurs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocateurs"
  - "bibliothèque C++ standard, allocateurs"
ms.assetid: ac95023b-9e7d-49f5-861a-bf7a9a340746
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Allocateurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les allocateurs sont utilisés par la bibliothèque STL \(Standard Template Library\) pour gérer l'allocation et la désallocation des éléments stockés dans des conteneurs.  Tous les conteneurs STL sauf std::array ont un paramètre de modèle de type `allocator<Type>`, où `Type` représente le type de l'élément conteneur.  Par exemple, la classe vector est déclarée comme suit :  
  
```  
template <  
    class Type,  
    class Allocator = allocator<Type>  
>  
class vector  
```  
  
 La bibliothèque STL fournit une implémentation par défaut pour un allocateur.  Dans C\+\+11 et versions ultérieures, l'allocateur par défaut est mis à jour pour exposer une interface plus petite. Le nouvel allocateur est appelé *allocateur minimal*.  En particulier, le membre `construct()` de l'allocateur minimal prend en charge la sémantique de déplacement, ce qui peut améliorer considérablement les performances.  Dans la plupart des cas, cet allocateur par défaut suffit.  Dans C\+\+11, tous les types et les fonctions de la bibliothèque STL qui acceptent un paramètre de type allocateur prennent en charge l'interface d'allocateur minimal, y compris `std::function`, `shared_ptr, allocate_shared()` et `basic_string`.  Pour plus d'informations sur l'allocateur par défaut, consultez [allocator, classe](../standard-library/allocator-class.md).  
  
## Écriture de votre propre allocateur \(C\+\+11\)  
 L'allocateur par défaut utilise `new` et `delete` pour allouer et désallouer la mémoire.  Si vous souhaitez utiliser une autre méthode d'allocation de la mémoire, telle que l'utilisation de la mémoire partagée, vous devez créer votre propre allocateur.  Si vous ciblez C\+\+11 et que vous devez écrire un nouvel allocateur personnalisé, faites\-en un allocateur minimal si possible.  Même si vous avez déjà implémenté un allocateur de style antérieur, il peut être préférable de le changer en *allocateur minimal* pour tirer parti de la méthode `construct()` plus efficace qui vous sera fournie automatiquement.  
  
 Un allocateur minimal nécessite beaucoup moins de code réutilisable et vous permet de vous concentrer sur les fonctions membres `allocate` et `deallocate` qui effectuent tout le travail.  Lors de la création d'un allocateur minimal, n'implémentez aucun membre à l'exception de ceux indiqués dans l'exemple ci\-dessous :  
  
1.  un constructeur de copie de conversion \(voir l'exemple\)  
  
2.  operator\=\=  
  
3.  operator\!\=  
  
4.  allocate  
  
5.  deallocate  
  
 Le membre `construct()` par défaut dans C\+\+11 qui vous sera fourni effectue un transfert parfait et autorise la sémantique de déplacement. Dans de nombreux cas, il est beaucoup plus efficace que l'ancienne version.  
  
> [!WARNING]
>  Au moment de la compilation, la bibliothèque STL utilise la classe allocator\_traits pour détecter les membres que vous avez fournis explicitement et fournit une implémentation par défaut pour tous les membres qui ne sont pas présents.  N'interférez pas avec ce mécanisme en fournissant une spécialisation d'allocator\_traits pour votre allocateur.  
  
 L'exemple suivant montre une implémentation minimale d'un allocateur qui utilise `malloc` et `free`.  Notez l'utilisation du nouveau type d'exception `std::bad_array_new_length` qui est levé si la taille du tableau est inférieure à zéro ou supérieure à la taille maximale autorisée.  
  
```  
#pragma once  
#include <stdlib.h> //size_t, malloc, free  
#include <new> // bad_alloc, bad_array_new_length  
#include <memory>  
template <class T>  
struct Mallocator  
{  
    typedef T value_type;  
    Mallocator() noexcept {} //default ctor not required by STL  
  
    // A converting copy constructor:  
    template<class U> Mallocator(const Mallocator<U>&) noexcept {}  
    template<class U> bool operator==(const Mallocator<U>&) const noexcept  
    {  
        return true;  
    }  
    template<class U> bool operator!=(const Mallocator<U>&) const noexcept  
    {  
        return false;  
    }  
    T* allocate(const size_t n) const;  
    void deallocate(T* const p, size_t) const noexcept;  
};  
  
template <class T>  
T* Mallocator<T>::allocate(const size_t n) const  
{  
    if (n == 0)  
    {  
        return nullptr;  
    }  
    if (n > static_cast<size_t>(-1) / sizeof(T))  
    {  
        throw std::bad_array_new_length();  
    }  
    void* const pv = malloc(n * sizeof(T));  
    if (!pv) { throw std::bad_alloc(); }  
    return static_cast<T*>(pv);  
}  
  
template<class T>  
void Mallocator<T>::deallocate(T * const p, size_t) const noexcept  
{  
    free(p);  
}  
```  
  
## Écriture de votre propre allocateur \(C\+\+03\)  
 Dans C\+\+03, tout allocateur utilisé avec des conteneurs STL doit implémenter les définitions de types suivantes :  
  
|||  
|-|-|  
|`const_pointer`|`rebind`|  
|`const_reference`|`reference`|  
|`difference_type`|`size_type`|  
|`pointer`|`value_type`|  
  
 En outre, tout allocateur utilisé avec des conteneurs STL doit implémenter les méthodes suivantes :  
  
|||  
|-|-|  
|Constructeur|`deallocate`|  
|Constructeur de copie|`destroy`|  
|Destructeur|`max_size`|  
|`address`|`operator==`|  
|`allocate`|`operator!=`|  
|`construct`||  
  
 Pour plus d'informations sur ces méthodes et définitions de types, consultez [allocator, classe](../standard-library/allocator-class.md).  
  
## Voir aussi  
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)