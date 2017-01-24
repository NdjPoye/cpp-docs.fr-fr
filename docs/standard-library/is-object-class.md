---
title: "is_object, classe | Microsoft Docs"
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
  - "is_object"
  - "std.tr1.is_object"
  - "std::tr1::is_object"
  - "std.is_object"
  - "std::is_object"
  - "type_traits/std::is_object"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_object (classe) (TR1)"
  - "is_object"
ms.assetid: b452ceea-5676-488f-925b-ab881126c387
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_object, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type est un type d'objet.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct is_object;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type contient la valeur false si le type `Ty` est un type référence, un type fonction ou void, ou une forme `cv-qualified` de l'un d'eux. Sinon, contient la valeur true.  
  
## Exemple  
  
```  
// std_tr1__type_traits__is_object.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct functional   
    {   
    int f();   
    };   
  
int main()   
    {   
    std::cout << "is_object<trivial> == " << std::boolalpha   
        << std::is_object<trivial>::value << std::endl;   
    std::cout << "is_object<functional> == " << std::boolalpha   
        << std::is_object<functional>::value << std::endl;   
    std::cout << "is_object<trivial&> == " << std::boolalpha   
        << std::is_object<trivial&>::value << std::endl;   
    std::cout << "is_object<float()> == " << std::boolalpha   
        << std::is_object<float()>::value << std::endl;   
    std::cout << "is_object<void> == " << std::boolalpha   
        << std::is_object<void>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_object\<trivial\> \=\= true**  
**is\_object\<functional\> \=\= true**  
**is\_object\<trivial&\> \=\= false**  
**is\_object\<float\(\)\> \=\= false**  
**is\_object\<void\> \=\= false**   
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_function, classe](../standard-library/is-function-class.md)