---
title: "aligned_union, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "aligned_union"
  - "std.aligned_union"
  - "std::aligned_union"
  - "type_traits/std::aligned_union"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aligned_union"
ms.assetid: 9931a44d-3a67-4f29-a0f6-d47a7cf560ac
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# aligned_union, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fournit un type POD suffisamment grand et aligné convenablement pour stocker un type d’union et la taille requise.  
  
## Syntaxe  
  
```  
template <std::size_t Len, class... Types>  
    struct aligned_union;  
  
template <std::size_t Len, class... Types>  
    using aligned_union_t = typename aligned_union<Len, Types...>::type;  
```  
  
#### Paramètres  
 `Len`  
 Valeur d'alignement pour le plus grand type dans l'union.  
  
 `Types`  
 Types distincts dans l'union sous\-jacente.  
  
## Notes  
 Utilisez la classe de modèle pour obtenir l’alignement et la taille nécessaire pour stocker une union de stockage. Le typedef de membre `type` noms POD tapez adaptés au stockage d’un type énuméré dans `Types`; la taille minimale est `Len`. Le membre statique `alignment_value` de type `std::size_t` contient l’alignement plus strict de tous les types répertoriés dans `Types`.  
  
## Exemple  
 L’exemple suivant montre comment utiliser `aligned_union` pour allouer un tampon de pile alignée pour placer une union.  
  
```  
// std__type_traits__aligned_union.cpp  
#include <iostream>  
#include <type_traits>  
  
union U_type  
{  
    int i;  
    float f;  
    double d;  
    U_type(float e) : f(e) {}  
};  
  
typedef std::aligned_union<16, int, float, double>::type aligned_U_type;  
  
int main()  
{  
    // allocate memory for a U_type aligned on a 16-byte boundary  
    aligned_U_type au;  
    // do placement new in the aligned memory on the stack  
    U_type* u = new (&au) U_type(1.0f);  
    if (nullptr != u)  
    {  
        std::cout << "value of u->i is " << u->i << std::endl;  
        // must clean up placement objects manually!  
        u->~U_type();  
    }  
}  
```  
  
```Output  
valeur d’u -> i est 1065353216  
```  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [alignment\_of, classe](../standard-library/alignment-of-class.md)