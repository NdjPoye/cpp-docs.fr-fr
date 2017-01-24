---
title: "is_compound, classe | Microsoft Docs"
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
  - "std::tr1::is_compound"
  - "is_compound"
  - "std.tr1.is_compound"
  - "std.is_compound"
  - "std::is_compound"
  - "type_traits/std::is_compound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_compound (classe) (TR1)"
  - "is_compound"
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
caps.latest.revision: 21
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_compound, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type spécifié n'est pas fondamental.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct is_compound;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur `false` si le type de `Ty` est un type fondamental \(autrement dit, si [is\_fundamental](../standard-library/is-fundamental-class.md)`<``Ty``>` contient `true`\). Sinon, elle a la valeur `true`.  Ainsi, le prédicat a la valeur `true` si `Ty` est un type tableau, un type fonction, un pointeur vers `void` ou un objet ou une fonction, une référence, une classe, une union, une énumération ou un pointeur vers un membre de classe non statique, ou une forme *cv\-qualified* de l'un d'eux.  
  
## Exemple  
  
```  
// std_tr1__type_traits__is_compound.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_compound<trivial> == " << std::boolalpha   
        << std::is_compound<trivial>::value << std::endl;   
    std::cout << "is_compound<int[]> == " << std::boolalpha   
        << std::is_compound<int[]>::value << std::endl;   
    std::cout << "is_compound<int()> == " << std::boolalpha   
        << std::is_compound<int()>::value << std::endl;   
    std::cout << "is_compound<int&> == " << std::boolalpha   
        << std::is_compound<int&>::value << std::endl;   
    std::cout << "is_compound<void *> == " << std::boolalpha   
        << std::is_compound<void *>::value << std::endl;   
    std::cout << "is_compound<int> == " << std::boolalpha   
        << std::is_compound<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_compound\<trivial\> \=\= true**  
**is\_compound\<int\[\]\> \=\= true**  
**is\_compound\<int\(\)\> \=\= true**  
**is\_compound\<int&\> \=\= true**  
**is\_compound\<void \*\> \=\= true**  
**is\_compound\<int\> \=\= false**   
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_class, classe](../standard-library/is-class-class.md)