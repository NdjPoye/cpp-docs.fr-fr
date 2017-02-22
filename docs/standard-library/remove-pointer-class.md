---
title: "remove_pointer, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "remove_pointer"
  - "std.tr1.remove_pointer"
  - "std::tr1::remove_pointer"
  - "std.remove_pointer"
  - "std::remove_pointer"
  - "type_traits/std::remove_pointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_pointer (classe) (TR1)"
  - "remove_pointer"
ms.assetid: 2cd4e417-32fb-4f53-bd16-4e8a98240832
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# remove_pointer, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Transforme un pointeur en type.  
  
## Syntaxe  
  
```  
template<class T>  
    struct remove_pointer;  
  
template<class T>  
  using remove_pointer_t = typename remove_pointer<T>::type;  
```  
  
#### Paramètres  
 `T`  
 Type à modifier.  
  
## Notes  
 Une instance de `remove_pointer<T>` contient un type modifié qui est `T1` quand `T` est au format `T1*`, `T1* const`, `T1* volatile` ou `T1* const volatile`. Sinon, `T`.  
  
## Exemple  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_pointer_t<int *> *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "remove_pointer_t<int *> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **remove\_pointer\_t\<int \*\> \=\= int**   
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [add\_pointer, classe](../standard-library/add-pointer-class.md)