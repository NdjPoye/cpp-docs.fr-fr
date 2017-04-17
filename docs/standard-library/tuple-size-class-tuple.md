---
title: tuple_size, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tuple_size
- std::tuple_size
- utility/std::tuple_size
dev_langs:
- C++
helpviewer_keywords:
- tuple_size Class
ms.assetid: 73852fc5-eb68-41f1-8379-465cedc2314a
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: f0ae102852f1db46b68d86438e20ce9645535d19
ms.lasthandoff: 02/24/2017

---
# <a name="tuplesize-class"></a>tuple_size, classe ;
Indique le nombre d’éléments qu’un `tuple` contient.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
// TEMPLATE STRUCT tuple_size  
template <class Tuple>  
   struct tuple_size;  
  
// number of elements in array  
template <class Elem, size_t Size>  
   struct tuple_size<array<Elem, Size>>  
      : integral_constant<size_t, Size>; 
  
// size of pair
template <class T1, class T2>
   struct tuple_size<pair<T1, T2>> 
      : integral_constant<size_t, 2>

// size of tuple  
template <class... Types>  
   struct tuple_size<tuple<Types...>>  
      : integral_constant<size_t, sizeof...(Types)>;  
  
// size of const tuple  
template <class Tuple>  
   struct tuple_size<const Tuple>;  
  
// size of volatile tuple  
template <class Tuple>  
   struct tuple_size<volatile Tuple>;  
  
// size of const volatile tuple  
template <class Tuple>  
   struct tuple_size<const volatile Tuple>;   
```  
  
#### <a name="parameters"></a>Paramètres  
*Tuple*  
Type du tuple. 
  
*Elem*  
Type des éléments du tableau. 
  
*Size*  
Taille du tableau. 
  
*T1*  
Type du premier membre de la paire. 
  
*T2*  
Type du second membre de la paire. 
  
*Types*  
Types des éléments de tuple. 
  
  
## <a name="remarks"></a>Notes  
La classe de modèle a un membre `value` qui est une expression constante entière dont la valeur est l’extension du type de tuple `Tuple`.  
  
La spécialisation de modèle pour les tableaux possède un membre `value` qui est une expression constante intégrale dont la valeur est `Size`, qui est la taille du tableau.  
  
La spécialisation de modèle pour une paire possède un membre `value` qui est une expression constante intégrale dont la valeur est 2.  
  
## <a name="example"></a>Exemple  
  
```cpp  
#include <tuple>   
#include <iostream>  
  
using namespace std;  
  
typedef tuple<int, double, int, double> MyTuple;  
int main()  
{  
    MyTuple c0(0, 1.5, 2, 3.7);  
  
    // display contents " 0 1 2 3"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0);  
    cout << " " << get<2>(c0);  
    cout << " " << get<3>(c0) << endl;  
  
    // display size " 4"   
    cout << " " << tuple_size<MyTuple>::value << endl;  
}  
```  
  
```Output  
 0 1.5 2 3.7  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<tuple>  
 **En-tête :** \<array> (pour la spécialisation de tableau)  
 **En-tête :** \<utility> (pour la spécialisation de paire)  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [\<tuple>](../standard-library/tuple.md)   
 [tuple](../standard-library/tuple-class.md)  
 [tuple_element, classe](../standard-library/tuple-element-class-tuple.md)
