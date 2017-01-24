---
title: "is_floating_point, classe | Microsoft Docs"
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
  - "is_floating_point"
  - "std.tr1.is_floating_point"
  - "std::tr1::is_floating_point"
  - "std.is_floating_point"
  - "std::is_floating_point"
  - "type_traits/std::is_floating_point"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_floating_point (classe) (TR1)"
  - "is_floating_point"
ms.assetid: 070679c1-115b-4ee4-8ab7-f52e5d9e157f
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_floating_point, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type est à virgule flottante.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct is_floating_point;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `Ty` est un type à virgule flottante ou une forme `cv-qualified` d'un type à virgule flottante. Sinon, sa valeur est false.  
  
 Un type à virgule flottante est `float`, `double` ou `long double`.  
  
## Exemple  
  
```  
// std_tr1__type_traits__is_floating_point.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_floating_point<trivial> == " << std::boolalpha   
        << std::is_floating_point<trivial>::value << std::endl;   
    std::cout << "is_floating_point<int> == " << std::boolalpha   
        << std::is_floating_point<int>::value << std::endl;   
    std::cout << "is_floating_point<float> == " << std::boolalpha   
        << std::is_floating_point<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_floating\_point\<trivial\> \=\= false**  
**is\_floating\_point\<int\> \=\= false**  
**is\_floating\_point\<float\> \=\= true**   
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_integral, classe](../standard-library/is-integral-class.md)