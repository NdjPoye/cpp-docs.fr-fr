---
title: "remove_extent, classe | Microsoft Docs"
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
  - "std::tr1::remove_extent"
  - "std.tr1.remove_extent"
  - "remove_extent"
  - "std.remove_extent"
  - "std::remove_extent"
  - "type_traits/std::remove_extent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_extent (classe) (TR1)"
  - "remove_extent"
ms.assetid: b9320862-3891-49fc-80bc-571eb2c035cf
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# remove_extent, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée un type d'élément à partir d'un type tableau.  
  
## Syntaxe  
  
```  
template<class T>  
    struct remove_extent;  
  
template<class T>  
using remove_extent_t = typename remove_extent<T>::type;  
```  
  
#### Paramètres  
 `T`  
 Type à modifier.  
  
## Notes  
 Une instance de `remove_extent<T>` contient un type modifié qui est `T1` quand `T` est de la forme `T1[N]`, ou `T` dans le cas contraire.  
  
## Exemple  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "remove_extent_t<int> == "  
        << typeid(std::remove_extent_t<int>).name()  
        << std::endl;T  
    std::cout << "remove_extent_t<int[5]> == "  
        << typeid(std::remove_extent_t<int[5]>).name()  
        << std::endl;T  
    std::cout << "remove_extent_t<int[5][10]> == "  
        << typeid(std::remove_extent_t<int[5][10]>).name()  
        << std::endl;   
    return (0);   
    }  
  
```  
  
  **remove\_extent\_t\<int\> \=\= int**  
**remove\_extent\_t\<int\[5\]\> \=\= int**  
**remove\_extent\_t\<int\[5\]\[10\]\> \=\= int \[10\]**   
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_all\_extents, classe](../standard-library/remove-all-extents-class.md)