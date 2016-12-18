---
title: "is_arithmetic, classe | Microsoft Docs"
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
  - "is_arithmetic"
  - "std.tr1.is_arithmetic"
  - "std::tr1::is_arithmetic"
  - "std.is_arithmetic"
  - "std::is_arithmetic"
  - "type_traits/std::is_arithmetic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_arithmetic (classe) (TR1)"
  - "is_arithmetic"
ms.assetid: ea427b7e-0141-4a04-848f-561054c53001
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_arithmetic, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type est arithmétique.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct is_arithmetic;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `Ty` est un type arithmétique, autrement dit un type intégral, un type à virgule flottante ou une forme `cv-qualified` de l'un d'eux. Sinon, sa valeur est false.  
  
## Exemple  
  
```  
// std_tr1__type_traits__is_arithmetic.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_arithmetic<trivial> == " << std::boolalpha   
        << std::is_arithmetic<trivial>::value << std::endl;   
    std::cout << "is_arithmetic<int> == " << std::boolalpha   
        << std::is_arithmetic<int>::value << std::endl;   
    std::cout << "is_arithmetic<float> == " << std::boolalpha   
        << std::is_arithmetic<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_arithmetic\<trivial\> \=\= false**  
**is\_arithmetic\<int\> \=\= true**  
**is\_arithmetic\<float\> \=\= true**   
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_floating\_point, classe](../standard-library/is-floating-point-class.md)   
 [is\_integral, classe](../standard-library/is-integral-class.md)