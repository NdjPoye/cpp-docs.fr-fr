---
title: "is_fundamental, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_fundamental"
  - "std.tr1.is_fundamental"
  - "std::tr1::is_fundamental"
  - "std.is_fundamental"
  - "std::is_fundamental"
  - "type_traits/std::is_fundamental"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_fundamental (classe) (TR1)"
  - "is_fundamental"
ms.assetid: b84eee84-2fb2-4611-beaf-b384074d8b6a
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_fundamental, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type est void ou arithmétique.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct is_fundamental;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `Ty` est un type fondamental, autrement dit `void`, un type intégral, un type à virgule flottante ou une forme `cv-qualified` de l'un d'eux. Sinon, sa valeur est false.  
  
## Exemple  
  
```  
// std_tr1__type_traits__is_fundamental.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_fundamental<trivial> == " << std::boolalpha   
        << std::is_fundamental<trivial>::value << std::endl;   
    std::cout << "is_fundamental<int> == " << std::boolalpha   
        << std::is_fundamental<int>::value << std::endl;   
    std::cout << "is_fundamental<const float> == " << std::boolalpha   
        << std::is_fundamental<const float>::value << std::endl;   
    std::cout << "is_fundamental<void> == " << std::boolalpha   
        << std::is_fundamental<void>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_fundamental\<trivial\> \=\= false**  
**is\_fundamental\<int\> \=\= true**  
**is\_fundamental\<const float\> \=\= true**  
**is\_fundamental\<void\> \=\= true**   
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_compound, classe](../standard-library/is-compound-class.md)