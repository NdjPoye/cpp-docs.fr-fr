---
title: "rank, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::rank"
  - "std.tr1.rank"
  - "rank"
  - "std.rank"
  - "std::rank"
  - "type_traits/std::rank"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rank (classe) (TR1)"
  - "rank"
ms.assetid: bc9f1b8f-800f-46ca-b6f4-d8579ed5406a
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# rank, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient le nombre de dimensions de tableau.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct rank;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
## Notes  
 La requête de type contient la valeur du nombre de dimensions du type tableau `Ty`, ou 0 si `Ty` n'est pas un type tableau.  
  
## Exemple  
  
```  
// std_tr1__type_traits__rank.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "rank<int> == "   
        << std::rank<int>::value << std::endl;   
    std::cout << "rank<int[5]> == "   
        << std::rank<int[5]>::value << std::endl;   
    std::cout << "rank<int[5][10]> == "   
        << std::rank<int[5][10]>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
rang < int > == < int [5] > de rang 0 == 1 rang < int [5] [10] > == 2  
```  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [extent, classe](../standard-library/extent-class.md)