---
title: "integral_constant (classe), bool_constant (classe) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.integral_constant"
  - "integral_constant"
  - "std::tr1::integral_constant"
  - "std.integral_constant"
  - "std::integral_constant"
  - "type_traits/std::integral_constant"
  - "std.bool_constant"
  - "std::bool_constant"
  - "type_traits/std::bool_constant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "integral_constant (classe) (TR1)"
  - "integral_constant"
  - "bool_constant"
ms.assetid: 11c002c6-4d31-4042-9341-f2543f43e108
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# integral_constant (classe), bool_constant (classe)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Rend un intégral constant à partir d’un type et une valeur.  
  
## Syntaxe  
  
```  
template <class T, T v>  
    struct integral_constant {  
        static constexpr T value = v;  
        typedef T value_type;  
        typedef integral_constant<T, v> type;  
        constexpr operator value_type() const noexcept { return (value); }  
        constexpr value_type operator()() const noexcept { return (value); }  
    };  
  
template <bool v>  
    using bool_constant = integral_constant<bool, v>;  
  
```  
  
#### Paramètres  
 `T`  
 Type de la constante.  
  
 `v`  
 Valeur de la constante.  
  
## Notes  
 La `integral_constant` classe de modèle lorsque spécialisé avec un type intégral `T` et une valeur `v` de ce type, représente un objet qui contient une constante de ce type intégral avec la valeur spécifiée. Le membre nommé `type` est un alias pour le type de spécialisation de modèle généré et le `value` membre conserve la valeur `v` utilisée pour créer la spécialisation.  
  
 La `bool_constant` classe de modèle est une spécialisation explicite de `integral_constant` qui utilise `bool` comme le `T` argument.  
  
## Exemple  
  
```cpp  
// std__type_traits__integral_constant.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "integral_constant<int, 5> == "   
        << std::integral_constant<int, 5>::value << std::endl;   
    std::cout << "integral_constant<bool, false> == " << std::boolalpha   
        << std::integral_constant<bool, false>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
integral_constant < int, 5 > == 5 integral_constant < bool, false > == false  
```  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [false\_type, typedef](../Topic/false_type%20Typedef.md)   
 [true\_type, typedef](../Topic/true_type%20Typedef.md)