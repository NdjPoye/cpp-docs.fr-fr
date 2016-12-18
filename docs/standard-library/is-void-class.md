---
title: "is_void, classe | Microsoft Docs"
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
  - "is_void"
  - "std.tr1.is_void"
  - "std::tr1::is_void"
  - "std.is_void"
  - "std::is_void"
  - "type_traits/std::is_void"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_void (classe) (TR1)"
  - "is_void"
ms.assetid: 99b0de3b-1b38-4949-b053-080e5363174e
caps.latest.revision: 21
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_void, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type est void.  
  
## Syntaxe  
  
```  
template<class T>  
    struct is_void;  
```  
  
#### Paramètres  
 `T`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est `void` ou une forme cv\-qualified de `void`. Sinon, sa valeur est false.  
  
## Exemple  
  
```cpp  
// std__type_traits__is_void.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_void<trivial> == " << std::boolalpha   
        << std::is_void<trivial>::value << std::endl;   
    std::cout << "is_void<void()> == " << std::boolalpha   
        << std::is_void<void()>::value << std::endl;   
    std::cout << "is_void<void> == " << std::boolalpha   
        << std::is_void<void>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_void<trivial> == false is_void<void()> == false is_void<void> == true  
```  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)