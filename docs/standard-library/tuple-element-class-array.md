---
title: "tuple_element, classe &lt;array&gt; | Microsoft Docs"
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
  - "std.tr1.tuple_element"
  - "tuple_element"
  - "std::tr1::tuple_element"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tuple_element, classe <array> (TR1)"
ms.assetid: 99201ca4-190a-4d9e-9013-de95ddfe5901
caps.latest.revision: 21
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tuple_element, classe &lt;array&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Encapsule le type d’un élément array.  
  
## Syntaxe  
  
```  
// CLASS tuple_element (find element by index)  
template<size_t Index, class Tuple>  
struct tuple_element;  
  
template<size_t Index, class T, size_t Size>  
struct tuple_element<Index, array<T, Size>>  
  
// tuple_element for const  
template<size_t Index, class Tuple>  
struct tuple_element<Index, const Tuple>;  
  
// tuple_element for volatile  
template<size_t Index, class Tuple>  
struct tuple_element<Index, volatile Tuple>;  
  
// tuple_element for const volatile  
template<size_t Index, class Tuple>  
struct tuple_element<Index, const volatile Tuple>;  
  
template<size_t Index, class Tuple>  
using tuple_element_t = typename tuple_element<Index, Tuple>::type;  
  
```  
  
## Paramètres  
 `Index`  
 Position de l’élément.  
  
 `T`  
 Type d’un élément.  
  
 `N`  
 Taille du tableau.  
  
## Notes  
 Cette classe de modèle est une spécialisation de la classe de modèle [tuple\_element, classe](../standard-library/tuple-element-class-tuple.md) pour les tableaux. Cette classe fournit une interface vers un tableau comme un tuple de N éléments, chacun d’entre eux ayant le même type. Chaque spécialisation a un typedef imbriqué `type` qui est un synonyme du type de l’élément `Index` du `array`, avec des qualifications const\-volatiles conservées.  
  
## Exemple  
  
```  
  
#include <array>   
#include <iostream>   
  
using namespace std;  
typedef array<int, 4> MyArray;  
  
int main()  
{  
    MyArray c0 { 0, 1, 2, 3 };  
  
    for (const auto& e : c0)  
    {  
        cout << " " << e;  
    }  
    cout << endl;  
  
    // display first element " 0"   
    tuple_element<0, MyArray>::type val = c0.front();  
    cout << " " << val << endl;  
}  
  
/*  
Output:  
0 1 2 3  
0  
*/  
  
```  
  
## Configuration requise  
 **En\-tête :** \<array\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<array\>](../standard-library/array.md)   
 [\<tuple\>](../standard-library/tuple.md)   
 [tuple\_element, classe](../standard-library/tuple-element-class-tuple.md)