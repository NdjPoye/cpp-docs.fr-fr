---
title: "remove_all_extents, classe | Microsoft Docs"
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
  - "std.tr1.remove_all_extents"
  - "std::tr1::remove_all_extents"
  - "remove_all_extents"
  - "std.remove_all_extents"
  - "std::remove_all_extents"
  - "type_traits/std::remove_all_extents"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_all_extents (classe) (TR1)"
  - "remove_all_extents"
ms.assetid: 548dc536-82e7-423a-b8c1-443d66d9632e
caps.latest.revision: 16
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# remove_all_extents, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Convertit un type tableau en un type autre qu'un type tableau.  
  
## Syntaxe  
  
```  
template<class T>  
    struct remove_all_extents;  
  
template<class T>  
  using remove_all_extents_t = typename remove_all_extents<T>::type;  
```  
  
#### Paramètres  
 `T`  
 Type à modifier.  
  
## Notes  
 Instance de `remove_all_extents<T>` contenant un type modifié correspondant au type d'élément du type tableau `T` avec toutes les dimensions de tableau supprimées, ou `T` si `T` n'est pas un type tableau.  
  
## Exemple  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "remove_all_extents<int> == "   
        << typeid(std::remove_all_extents_t<int>).name()   
        << std::endl;   
    std::cout << "remove_all_extents_t<int[5]> == "   
        << typeid(std::remove_all_extents_t<int[5]>).name()   
        << std::endl;   
    std::cout << "remove_all_extents_t<int[5][10]> == "   
        << typeid(std::remove_all_extents_t<int[5][10]>).name()   
        << std::endl;   
  
    return (0);   
    }  
  
```  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_extent, classe](../standard-library/remove-extent-class.md)