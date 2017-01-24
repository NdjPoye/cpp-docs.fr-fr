---
title: "extent, classe | Microsoft Docs"
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
  - "std.tr1.extent"
  - "extent"
  - "std::tr1::extent"
  - "std.extent"
  - "std::extent"
  - "type_traits/std::extent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "extent (classe) (TR1)"
  - "extent"
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# extent, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient une dimension de tableau.  
  
## Syntaxe  
  
```  
template<class Ty, unsigned I = 0>  
    struct extent;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
 `I`  
 Tableau lié à interroger.  
  
## Notes  
 Si `Ty` est un type tableau qui possède au moins `I` dimensions, la requête de type contient le nombre d'éléments dans la dimension spécifié par `I`.  Si `Ty` n'est pas un type tableau ou si son rang est inférieur à `I`, ou si `I` est égal à zéro et que `Ty` est de type « tableau ayant des limites d'index inconnues de `U` », la requête de type contient la valeur 0.  
  
## Exemple  
  
```  
// std_tr1__type_traits__extent.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "extent 0 == "   
        << std::extent<int[5][10]>::value << std::endl;   
    std::cout << "extent 1 == "   
        << std::extent<int[5][10], 1>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **extent 0 \=\= 5**  
**extent 1 \=\= 10**   
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_all\_extents, classe](../standard-library/remove-all-extents-class.md)   
 [remove\_extent, classe](../standard-library/remove-extent-class.md)