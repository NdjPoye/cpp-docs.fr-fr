---
title: "add_pointer, classe | Microsoft Docs"
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
  - "std::tr1::add_pointer"
  - "std.tr1.add_pointer"
  - "add_pointer"
  - "std.add_pointer"
  - "std::add_pointer"
  - "type_traits/std::add_pointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_pointer (classe) (TR1)"
  - "add_pointer"
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
caps.latest.revision: 22
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# add_pointer, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée un pointeur vers un type à partir d'un type spécifié.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct add_pointer;  
  
template<class T>  
using add_pointer_t = typename add_pointer<T>::type;  
```  
  
#### Paramètres  
 `Ty`  
 Type à modifier.  
  
## Notes  
 Le type typedef de membre nomme le même type que `remove_reference<T>::type*`.  
  
 Comme il n'est pas valide de créer un pointeur à partir d'une référence, `add_pointer` supprime la référence, le cas échéant, du type spécifié avant de créer un pointeur vers un type.  Par conséquent, vous pouvez utiliser un type avec `add_pointer` sans vous soucier de savoir si ce type est une référence.  
  
## Exemple  
 L'exemple suivant montre que l'objet `add_pointer` d'un type est le même qu'un pointeur vers ce type.  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::add_pointer_t<int> *p = (int **)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_pointer_t<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **add\_pointer\_t\<int\> \=\= int \***   
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_pointer, classe](../standard-library/remove-pointer-class.md)