---
title: "multiplies, struct | Microsoft Docs"
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
  - "std::multiplies"
  - "multiplies"
  - "xfunctional/std::multiplies"
  - "std.multiplies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multiplies (classe)"
  - "multiplies (struct)"
ms.assetid: ec85e8af-70ad-44ad-90f0-d961a5847864
caps.latest.revision: 21
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# multiplies, struct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un objet de fonction prédéfinie qui exécute l'opération multiplication \( `operator*`\) à ses arguments.  
  
## Syntaxe  
  
```  
template<class Type = void>  
   struct multiplies : public binary_function <Type, Type, Type>   
   {  
      Type operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator*  
template<>  
   struct multiplies<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
         -> decltype(std::forward<Type1>(Left)  
            * std::forward<Type2>(Right));  
   };  
  
```  
  
#### Paramètres  
 `Type`, `Type1`, `Type2`  
 Un type qui prend en charge un `operator*` binaire qui prend des opérandes des types spécifiés ou déduits.  
  
 `Left`  
 L'opérande gauche de l'opération multiplication.  Le modèle non spécialisé prend un argument de référence lvalue de type `Type`.  Le modèle spécialisé perfectionne le transfert des arguments de référence lvalue et rvalue de type déduit `Type1`.  
  
 `Right`  
 L'opérande droit de l'opération multiplication.  Le modèle non spécialisé prend un argument de référence lvalue de type `Type`.  Le modèle spécialisé perfectionne le transfert des arguments de référence lvalue et rvalue de type déduit `Type2`.  
  
## Valeur de retour  
 Le résultat de `Left` \* `*` \+ `Right`.  Le modèle spécialisé effectue de façon parfaite le transfert du résultat, qui a le type retourné par `operator*`.  
  
## Exemple  
  
```  
// functional_multiplies.cpp  
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
      v1.push_back( 2 * i );  
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
  
   // Finding the element-wise products of the elements of v1 & v2  
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),   
      multiplies<int>( ) );  
  
   cout << "The element-wise products of vectors V1 & v2\n are: ( " ;  
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )  
      cout << *Iter3 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **Le vecteur v1 \= \(2 4 6 8 10 12\)**  
**Le vecteur v2 \= \( 3 6 9 12 15 18 \)**  
**Les produits en ce qui concerne les éléments des vecteurs V1 & v2**  
 **comprennent notamment : \(6 24 54 96 150 216\)**   
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)