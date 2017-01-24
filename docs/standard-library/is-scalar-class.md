---
title: "is_scalar, classe | Microsoft Docs"
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
  - "std.tr1.is_scalar"
  - "std::tr1::is_scalar"
  - "is_scalar"
  - "std.is_scalar"
  - "std::is_scalar"
  - "type_traits/std::is_scalar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_scalar (classe) (TR1)"
  - "is_scalar"
ms.assetid: a0cdfc9a-f27e-4808-890f-6ed7942db60c
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_scalar, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type est scalaire.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct is_scalar;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `Ty` est un type intégral, un type à virgule flottante, un type énumération, un type pointeur, un pointeur vers un type de membre ou une forme `cv-qualified` de l'un d'eux. Sinon, sa valeur est false.  
  
## Exemple  
  
```  
// std_tr1__type_traits__is_scalar.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_scalar<trivial> == " << std::boolalpha   
        << std::is_scalar<trivial>::value << std::endl;   
    std::cout << "is_scalar<trivial *> == " << std::boolalpha   
        << std::is_scalar<trivial *>::value << std::endl;   
    std::cout << "is_scalar<int> == " << std::boolalpha   
        << std::is_scalar<int>::value << std::endl;   
    std::cout << "is_scalar<float> == " << std::boolalpha   
        << std::is_scalar<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_scalar\<trivial\> \=\= false**  
**is\_scalar\<trivial \*\> \=\= true**  
**is\_scalar\<int\> \=\= true**  
**is\_scalar\<float\> \=\= true**   
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_compound, classe](../standard-library/is-compound-class.md)