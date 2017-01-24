---
title: "is_class, classe | Microsoft Docs"
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
  - "is_class"
  - "std::tr1::is_class"
  - "std.tr1.is_class"
  - "std.is_class"
  - "std::is_class"
  - "type_traits/std::is_class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_class (classe) (TR1)"
  - "is_class"
ms.assetid: 96fc34a3-a81b-4ec6-b7fb-baafde1a0f4e
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_class, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type est une classe.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct is_class;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `Ty` est un type défini comme `class` ou `struct`, ou comme une forme `cv-qualified` de l'un d'eux. Sinon, sa valeur est false.  
  
## Exemple  
  
```  
// std_tr1__type_traits__is_class.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_class<trivial> == " << std::boolalpha   
        << std::is_class<trivial>::value << std::endl;   
    std::cout << "is_class<int> == " << std::boolalpha   
        << std::is_class<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_class\<trivial\> \=\= true**  
**is\_class\<int\> \=\= false**   
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_compound, classe](../standard-library/is-compound-class.md)   
 [is\_union, classe](../standard-library/is-union-class.md)