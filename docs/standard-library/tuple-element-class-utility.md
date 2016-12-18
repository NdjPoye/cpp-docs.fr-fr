---
title: "tuple_element, classe &lt;utility&gt; | Microsoft Docs"
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
  - "tuple_element, classe <utility> (TR1)"
ms.assetid: f9db79e8-685c-49e3-97ee-81763e516ce3
caps.latest.revision: 20
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tuple_element, classe &lt;utility&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Encapsule le type d’un élément `pair`.  
  
## Syntaxe  
  
```  
// CLASS tuple_element (find element by index)  
template<size_t Index, class Tuple>  
struct tuple_element;  
  
// struct to determine type of element 0 in pair  
template<class Ty1, class Ty2>  
struct tuple_element<0, pair<Ty1, Ty2> >;  
  
// struct to determine type of element 1 in pair  
template<class Ty1, class Ty2>  
struct tuple_element<1, pair<Ty1, Ty2> >;  
  
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
  
#### Paramètres  
 Index  
 La position de l’élément ; pour la paire, cette valeur est 0 ou 1.  
  
 `T1`  
 Type du premier élément de la paire.  
  
 `T2`  
 Type du deuxième élément de la paire.  
  
 type  
  
## Notes  
 Les modèles sont des spécialisations de la classe de modèle [tuple\_element, classe](../standard-library/tuple-element-class-tuple.md). Chacun a un typedef de membre unique, `type`, qui est un synonyme du type de l’élément à la position spécifiée dans la `pair`, avec des qualifications const et\/ou volatiles conservées.`tuple_element_t` est un alias pratique pour `tuple_element<N, pair<T1, T2>>::type`. Utilisez le [Fonction get](../Topic/get%20Function%20%3Cutility%3E.md) pour retourner l’élément à une position spécifiée ou \(dans C \+\+ 14 \/ Visual Studio 2015\) d’un type spécifié.  
  
## Exemple  
  
```  
#include <utility>   
#include <iostream>   
  
using namespace std;  
  
typedef pair<int, double> MyPair;  
int main()  
{  
    MyPair c0(0, 1.333);  
  
    // display contents " 0 1"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0) << endl;  
  
    // display first element " 0" by index  
    tuple_element<0, MyPair>::type val = get<0>(c0);  
    cout << " " << val;  
  
    // display second element by type   
    tuple_element<1, MyPair>::type val2 = get<double>(c0);  
    cout << " " << val2 << endl;  
}  
  
/*  
Output:  
0 1.333  
0 1.333  
*/  
```  
  
## Configuration requise  
 **En\-tête :** \<utility\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<utility\>](../standard-library/utility.md)   
 [Fonction get](../Topic/get%20Function%20%3Cutility%3E.md)   
 [tuple\_size, classe](../standard-library/tuple-size-class-utility.md)