---
title: "is_member_pointer, classe | Microsoft Docs"
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
  - "std::tr1::is_member_pointer"
  - "is_member_pointer"
  - "std.tr1.is_member_pointer"
  - "std.is_member_pointer"
  - "std::is_member_pointer"
  - "type_traits/std::is_member_pointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_member_pointer (classe) (TR1)"
  - "is_member_pointer"
ms.assetid: da07ff4e-9ee0-4baa-ad93-1741f10913d1
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_member_pointer, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type pointeur vers le membre.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct is_member_pointer;  
```  
  
#### Paramètres  
 `Ty`  
 Le type à la requête.  
  
## Notes  
 Une instance de l'attribut de type contient la valeur true si le type `Ty` pointeur vers la fonction membre ou un pointeur vers l'objet membre, soit une forme d'`cv-qualified` de l'un d'entre eux, sinon elle contient FALSE.  
  
## Exemple  
  
```  
// std_tr1__type_traits__is_member_pointer.cpp   
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
    std::cout << "is_member_pointer<trivial *> == "   
        << std::boolalpha   
        << std::is_member_pointer<trivial *>::value   
        << std::endl;   
    std::cout << "is_member_pointer<int trivial::*> == "   
        << std::boolalpha   
        << std::is_member_pointer<int trivial::*>::value   
        << std::endl;   
    std::cout << "is_member_pointer<int (functional::*)()> == "   
        << std::boolalpha   
        << std::is_member_pointer<int (functional::*)()>::value   
        << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_member\_pointertrivial\<\*\> \=\= false**  
**\=\=\<de trivial::\*\> d'is\_member\_pointerint true**  
**\=\=\<de \(functional::\*\)\(\)\> d'is\_member\_pointerint true**   
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_member\_function\_pointer, classe](../standard-library/is-member-function-pointer-class.md)   
 [is\_member\_object\_pointer, classe](../standard-library/is-member-object-pointer-class.md)   
 [is\_pointer, classe](../standard-library/is-pointer-class.md)