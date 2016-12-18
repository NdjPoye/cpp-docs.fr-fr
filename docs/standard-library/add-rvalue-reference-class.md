---
title: "add_rvalue_reference, classe | Microsoft Docs"
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
  - "type_traits/std::add_rvalue_reference"
  - "std::add_rvalue_reference"
  - "add_rvalue_reference"
  - "std.add_rvalue_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_rvalue_reference, classe"
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
caps.latest.revision: 11
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# add_rvalue_reference, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée un type de référence rvalue du paramètre de modèle, s’il s’agit d’un type d’objet ou une fonction. Dans le cas contraire, en raison de la sémantique de réduction de référence, le type est le même que le paramètre de modèle.  
  
## Syntaxe  
  
```cpp  
template<class T>  
    struct add_rvalue_reference;  
  
template<class T>  
    using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;  
```  
  
#### Paramètres  
 T  
 Type à modifier.  
  
## Notes  
 La `add_rvalue_reference` classe a un membre nommé `type`, qui est un alias pour le type d’une référence rvalue au paramètre de modèle `T`. La sémantique de réduction de référence implique que, pour les types non\-object et sans fonction `T`, `T&&` est un `T`. Par exemple, lorsque `T` est un type de référence lvalue,  `add_rvalue_reference<T>::type` est le type de référence lvalue, pas une référence rvalue.  
  
 Pour plus de commodité, \< type\_traits \> définit un modèle d’assistance, `add_rvalue_reference_t`, qui alias le `type` membre `add_rvalue_reference`.  
  
## Exemple  
 Cet exemple de code utilise static\_assert pour montrer comment les types de référence rvalue sont créés à l’aide de `add_rvalue_reference` et `add_rvalue_reference_t`, et la manière dont le résultat de `add_rvalue_reference` sur une référence lvalue type n’est pas une référence rvalue, mais réduit pour le type de référence lvalue.  
  
```cpp  
// ex_add_rvalue_reference.cpp  
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp  
#include <type_traits>   
#include <iostream>   
#include <string>  
  
using namespace std;  
int main()  
{  
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,   
        "Expected add_rvalue_reference_t<string> to be string&&");  
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,   
        "Expected add_rvalue_reference_t<string*> to be string*&&");  
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,   
        "Expected add_rvalue_reference_t<string&> to be string&");  
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,   
        "Expected add_rvalue_reference_t<string&&> to be string&&");  
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;  
    return 0;  
}  
  
/*Output:  
All static_assert tests of add_rvalue_reference passed.  
*/  
```  
  
## Configuration requise  
 En\-tête : \<type\_traits\> Espace de noms : std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [add\_lvalue\_reference, classe](../standard-library/add-lvalue-reference-class.md)   
 [is\_rvalue\_reference, classe](../standard-library/is-rvalue-reference-class.md)