---
title: "remove_cv, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "remove_cv"
  - "std::tr1::remove_cv"
  - "std.tr1.remove_cv"
  - "std.remove_cv"
  - "std::remove_cv"
  - "type_traits/std::remove_cv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_cv (classe) (TR1)"
  - "remove_cv"
ms.assetid: 8502602a-1c80-479c-84e0-33bd1d6496d6
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# remove_cv, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Rend un type non volatile ou non const.  
  
## Syntaxe  
  
```  
template<class T>  
    struct remove_cv;  
  
template<class T>  
  using remove_cv_t = typename remove_cv<T>::type;  
```  
  
#### Paramètres  
 `T`  
 Type à modifier.  
  
## Notes  
 Une instance de `remove_cv<T>` contient un type modifié qui est `T1` quand `T` est au format `const T1`, `volatile T1` ou `const volatile T1`. Sinon, `T`.  
  
## Exemple  
  
```  
  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_cv_t<const volatile int> *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "remove_cv_t<const volatile int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **remove\_cv\_t\<const volatile int\> \=\= int**   
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_const, classe](../standard-library/remove-const-class.md)   
 [remove\_volatile, classe](../standard-library/remove-volatile-class.md)