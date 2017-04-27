---
title: modulus, struct | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- modulus
- xfunctional/std::modulus
dev_langs:
- C++
helpviewer_keywords:
- modulus class
- modulus struct
ms.assetid: 86d342f7-b7b1-46a4-b0bb-6b7ae827369b
caps.latest.revision: 20
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
ms.openlocfilehash: 430f1f9c0fcc58e3b4bfef167356960eb132b3f7
ms.lasthandoff: 02/24/2017

---
# <a name="modulus-struct"></a>modulus, struct
Objet de fonction prédéfini qui effectue l’opération de division de modulo (`operator%`) sur ses arguments.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Type = void>
struct modulus : public binary_function <Type, Type, Type>  
{
    Type operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator%
template <>
struct modulus<void>  
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) % std::forward<U>(Right));
};
```  
  
#### <a name="parameters"></a>Paramètres  
 `Type`, `T`, `U`  
 Tout type qui prend en charge un `operator%` qui accepte des opérandes des types spécifiés ou inférés.  
  
 `Left`  
 Opérande gauche de l’opération de modulo. Le modèle non spécialisé prend un argument de référence lvalue de type `Type`. Le modèle spécialisé effectue un transfert parfait des arguments de référence lvalue et rvalue du type inféré `T`.  
  
 `Right`  
 Opérande droit de l’opération de modulo. Le modèle non spécialisé prend un argument de référence lvalue de type `Type`. Le modèle spécialisé effectue un transfert parfait des arguments de référence lvalue et rvalue du type inféré `U`.  
  
## <a name="return-value"></a>Valeur de retour  
 Résultat de `Left``%``Right`. Le modèle spécialisé effectue un transfert parfait du résultat, qui a le type retourné par `operator%`.  
  
## <a name="remarks"></a>Notes  
 Le foncteur `modulus` est limité aux types intégraux pour les types de données de base ou aux types définis par l'utilisateur qui implémentent `operator%`.  
  
## <a name="example"></a>Exemple  
  
```cpp  
// functional_modulus.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   vector <int> v1, v2, v3 ( 6 );  
   vector <int>::iterator Iter1, Iter2, Iter3;  
  
   int i;  
   for ( i = 1 ; i <= 6 ; i++ )  
   {  
      v1.push_back( 5 * i );  
   }  
  
   int j;  
   for ( j = 1 ; j <= 6 ; j++ )  
   {  
      v2.push_back( 3 * j );  
   }  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "The vector v2 = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
  
   // Finding the element-wise remainders of the elements of v1 & v2  
   transform (v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),   
      modulus<int>() );  
  
   cout << "The element-wise remainders of the modular division\n are: ( " ;  
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )  
      cout << *Iter3 << " ";  
   cout << ")" << endl;  
}  
/* Output:  
The vector v1 = ( 5 10 15 20 25 30 )  
The vector v2 = ( 3 6 9 12 15 18 )  
The element-wise remainders of the modular division  
 are: ( 2 4 6 8 10 12 )  
 */  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<functional>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)




