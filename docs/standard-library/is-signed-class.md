---
title: "is_signed, classe | Microsoft Docs"
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
  - "is_signed"
  - "std.tr1.is_signed"
  - "std::tr1::is_signed"
  - "std.is_signed"
  - "std::is_signed"
  - "type_traits/std::is_signed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_signed (classe) (TR1)"
  - "is_signed"
ms.assetid: 20ae44d9-22ad-4fbd-b26a-f18c62689451
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_signed, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Tester si le type est entier signé.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct is_signed;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `Ty` est un type intégral signé ou un type intégral signé `cv-qualified`. Sinon, sa valeur est false.  
  
## Exemple  
  
```  
// std_tr1__type_traits__is_signed.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_signed<trivial> == " << std::boolalpha   
        << std::is_signed<trivial>::value << std::endl;   
    std::cout << "is_signed<int> == " << std::boolalpha   
        << std::is_signed<int>::value << std::endl;   
    std::cout << "is_signed<unsigned int> == " << std::boolalpha   
        << std::is_signed<unsigned int>::value << std::endl;   
    std::cout << "is_signed<float> == " << std::boolalpha   
        << std::is_signed<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_signed\<trivial\> \=\= false**  
**is\_signed\<int\> \=\= true**  
**is\_signed\<unsigned int\> \=\= false**  
**is\_signed\<float\> \=\= false**   
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_unsigned, classe](../standard-library/is-unsigned-class.md)