---
title: greater, struct | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- greater
- xfunctional/std::greater
dev_langs:
- C++
helpviewer_keywords:
- greater struct
- greater function
ms.assetid: ebc348e1-edcd-466b-b21a-db95bd8f9079
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: bcb6c83709d8e0effc202ecfb13659e7f725b1d1
ms.lasthandoff: 02/24/2017

---
# <a name="greater-struct"></a>greater, struct
Prédicat binaire qui effectue l’opération Supérieur à ( `operator>`) sur ses arguments.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Type = void>
struct greater : public binary_function <Type, Type, bool>  
{
    bool operator()(
    const Type& Left,
    const Type& Right) const;

 };

// specialized transparent functor for operator>
template <>
struct greater<void>  
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const
    ->  decltype(std::forward<T>(Left)> std::forward<U>(Right));
 };
```  
  
#### <a name="parameters"></a>Paramètres  
 `Type`, `T`, `U`  
 Tout type qui prend en charge un `operator>` qui accepte des opérandes des types spécifiés ou inférés.  
  
 `Left`  
 Opérande gauche de l’opération Supérieur à. Le modèle non spécialisé prend un argument de référence lvalue de type `Type`. Le modèle spécialisé effectue un transfert parfait des arguments de référence lvalue et rvalue du type inféré `T`.  
  
 `Right`  
 Opérande droit de l’opération Supérieur à. Le modèle non spécialisé prend un argument de référence lvalue de type `Type`. Le modèle spécialisé effectue un transfert parfait des arguments de référence lvalue et rvalue du type inféré `U`.  
  
## <a name="return-value"></a>Valeur de retour  
 Résultat de `Left``>``Right`. Le modèle spécialisé effectue un transfert parfait du résultat, qui a le type retourné par `operator>`.  
  
## <a name="remarks"></a>Notes  
 Le prédicat binaire `greater`< `Type`> fournit un ordre faible strict d’un ensemble de valeurs d’élément de type `Type` dans des classes d’équivalence, si et seulement si ce type remplit les conditions mathématiques standard pour être ordonné de cette façon. Les spécialisations de tout type pointeur produisent un ordre total des éléments, dans le sens où tous les éléments de valeurs distinctes sont ordonnés les uns par rapport aux autres.  
  
## <a name="example"></a>Exemple  
  
```cpp  
// functional_greater.cpp  
// compile with: /EHsc  
#include <vector>  
#include <algorithm>  
#include <functional>  
#include <cstdlib>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
   vector <int>::iterator Iter1;  
  
   int i;  
   for ( i = 0 ; i < 8 ; i++ )  
   {  
      v1.push_back( rand( ) );  
   }  
  
   cout << "Original vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in ascending order,  
   // use default binary predicate less<int>( )  
   sort( v1.begin( ), v1.end( ) );  
   cout << "Sorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in descending order,   
   // specify binary predicate greater<int>( )  
   sort( v1.begin( ), v1.end( ), greater<int>( ) );  
   cout << "Resorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
}  
```  
  
## <a name="output"></a>Sortie  
  
```
Original vector v1 = (41 18467 6334 26500 19169 15724 11478 29358)
Sorted vector v1 = (41 6334 11478 15724 18467 19169 26500 29358)
Resorted vector v1 = (29358 26500 19169 18467 15724 11478 6334 41)
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<functional>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Référence de bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)




