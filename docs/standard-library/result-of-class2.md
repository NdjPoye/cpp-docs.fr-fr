---
title: "result_of, classe | Microsoft Docs"
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
  - "functional/std::tr1::result_of"
  - "std::tr1::result_of"
  - "result_of"
  - "std.tr1.result_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "result_of (classe) (TR1)"
ms.assetid: 14ec0040-07f1-45a5-80b5-d0c9f9b00c8f
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# result_of, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le type de retour d'un objet emballé appelable.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct result_of {  
    typedef T0 type;  
    };  
```  
  
#### Paramètres  
 `Ty`  
 Description d'un appel de fonction \(consultez la section Notes\).  
  
## Notes  
 La classe de modèle définit son membre `type` comme synonyme du type de retour d'un appel de fonction décrit par son argument de modèle `Ty`.  L'argument de modèle doit être de la forme `Fty(T1, T2, ..., TN)`, où `Fty` est un type appelable.  Le modèle détermine le type de retour selon la première des règles suivantes qui s'applique:  
  
-   si `Fty` un pointeur pour le type de fonction `R(*)(U1, U2, ..., UN)` le type de retour est `R`;  
  
-   Si `Fty` une référence pour le type de fonction `R(&)(U1, U2, ..., UN)` Le type de retour est `R`;  
  
-   si `Fty` un pointeur pour le type de fonction membre `R(U1::*)(U2, ..., UN)` le type de retour est `R`;  
  
-   si `Fty` est un pointeur pour le type de données membre `R U1::*` le type de retour est `R`;  
  
-   si `Fty` est une classe avec un membre typedef `result_type` le type de retour est `Fty::result_type`;  
  
-   si `N` est 0 \(autrement dit, `Ty` est au format `Fty()`\) que le type de retour est `void`;  
  
-   si `Fty` est une classe avec un modèle membre nommé `result` le type de retour est `Fty::result<T1, T2, ..., TN>::type`;  
  
-   dans tous les autres cas il s'agit d'une erreur.  
  
## Exemple  
  
```  
// std_tr1__functional__result_of.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
double square(double x)   
    {   
    return (x * x);   
    }   
  
template<class Fun,   
    class Arg>   
    void test_result(const Fun& fun, Arg arg)   
    {   
    typename std::result_of<Fun(Arg)>::type val = fun(arg);   
    std::cout << "val == " << val << std::endl;   
    }   
  
int main()   
    {   
    test_result(&square, 3.0);   
  
    return (0);   
    }  
  
```  
  
  **val \=\= 9**   
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std