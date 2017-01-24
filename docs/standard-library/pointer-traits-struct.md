---
title: "pointer_traits, struct | Microsoft Docs"
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
  - "memory/std::pointer_traits::element_type"
  - "memory/std::pointer_traits::pointer"
  - "memory/std::pointer_traits"
  - "memory/std::pointer_traits::difference_type"
  - "memory/std::pointer_traits::rebind"
  - "xmemory0/std::pointer_traits::element_type"
  - "xmemory0/std::pointer_traits::pointer"
  - "xmemory0/std::pointer_traits"
  - "xmemory0/std::pointer_traits::difference_type"
  - "xmemory0/std::pointer_traits::rebind"
dev_langs: 
  - "C++"
ms.assetid: 545aecf1-3561-4859-8b34-603c079fe1b3
caps.latest.revision: 13
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pointer_traits, struct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fournit les informations requises par un objet de classe de modèle `allocator_traits` pour décrire un allocateur avec un type pointeur `Ptr`.  
  
## Syntaxe  
  
```cpp  
template<class Ptr>  
    struct pointer_traits;  
```  
  
## Notes  
 Ptr peut être un pointeur brut de type `Ty *` ou une classe avec les propriétés suivantes.  
  
```  
template<class Ty, class... Rest>  
    struct Ptr  
    { // describes a pointer type usable by allocators  
    typedef Ptr pointer;  
    typedef T1 element_type; // optional  
    typedef T2 difference_type; // optional  
    template<class Other>  
        using rebind = typename Ptr<Other, Rest...>; // optional  
  
    static pointer pointer_to(element_type& obj); // optional  
    };  
```  
  
> [!WARNING]
>  Lorsque la norme C\+\+ spécifie le membre `rebind` en tant que modèle d'alias, les outils Visual C\+\+ implémentent rebind en tant que `struct`.  
  
### Typedef  
  
|Nom|Description|  
|---------|-----------------|  
|`typedef T2 difference_type`|Le type `T2` est `Ptr::difference_type` si ce type existe ; sinon `ptrdiff_t`.  Si `Ptr` est un pointeur brut, le type est `ptrdiff_t`.|  
|`typedef T1 element_type`|Le type `T1` est `Ptr::element_type` si ce type existe ; sinon `Ty`.  Si `Ptr` est un pointeur brut, le type est `Ty`.|  
|`typedef Ptr pointer`|Le type est `Ptr`.|  
  
### Structures  
  
|Nom|Description|  
|---------|-----------------|  
|`pointer_traits::rebind`|Tente de convertir le type de pointeur sous\-jacent en un type spécifié.|  
  
### Méthodes  
  
|Nom|Description|  
|---------|-----------------|  
|[pointer\_traits::pointer\_to, méthode](../Topic/pointer_traits::pointer_to%20Method.md)|Convertit une référence arbitraire à un objet de la classe `Ptr`.|  
  
## Configuration requise  
 **En\-tête:** \<mémoire\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<memory\>](../standard-library/memory.md)   
 [allocator\_traits, classe](../standard-library/allocator-traits-class.md)