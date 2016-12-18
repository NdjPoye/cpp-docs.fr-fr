---
title: "tuple_size, classe &lt;utility&gt; | Microsoft Docs"
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
  - "tuple_size"
  - "std::tr1::tuple_size"
  - "std.tr1.tuple_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tuple_size, classe <utility> (TR1)"
ms.assetid: 36d04207-ed87-4c11-9875-150c59833b79
caps.latest.revision: 21
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tuple_size, classe &lt;utility&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Encapsule le nombre d’éléments `pair`.  
  
## Syntaxe  
  
```  
template<class Tuple>  
struct tuple_size;  
  
template<class T1, class T2>  
struct tuple_size<pair<T1, T2>>   : integral_constant<size_t, 2>  
  
// size of const tuple  
template<class Tuple>  
struct tuple_size<const Tuple>;  
  
// size of volatile tuple  
template<class Tuple>  
struct tuple_size<volatile Tuple>;  
  
// size of const volatile tuple  
template<class Tuple>  
struct tuple_size<const volatile Tuple>;  
```  
  
#### Paramètres  
 `T1`  
 Type du premier élément de la paire.  
  
 `T2`  
 Type du deuxième élément de la paire.  
  
## Notes  
 Le modèle est une spécialisation de la classe de modèle [tuple\_size, classe](../standard-library/tuple-size-class-tuple.md). Il possède un membre `value` qui est une expression constante intégrale dont la valeur est 2.  
  
## Exemple  
  
```  
#include <utility>   
#include <iostream>   
  
using namespace std;  
  
typedef pair<int, double> MyPair;  
  
int main()  
{  
    MyPair c0(0, 1.1);  
  
    // display contents " 0 1.1"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0) << endl;  
  
    // display size " 2"   
    cout << " " << tuple_size<MyPair>::value << endl;  
  
}  
  
/*  
Output:  
0 1.1  
2  
*/  
```  
  
## Configuration requise  
 **En\-tête :** \<utility\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<utility\>](../standard-library/utility.md)   
 [Fonction get](../Topic/get%20Function%20%3Cutility%3E.md)   
 [tuple\_element, classe](../standard-library/tuple-element-class-utility.md)