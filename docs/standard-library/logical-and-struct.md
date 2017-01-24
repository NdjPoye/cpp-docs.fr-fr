---
title: "logical_and, struct | Microsoft Docs"
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
  - "std::logical_and"
  - "xfunctional/std::logical_and"
  - "std.logical_and"
  - "logical_and"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "logical_and (classe)"
  - "logical_and (struct)"
ms.assetid: 1a375cc2-0592-4d57-a553-78009c7ad610
caps.latest.revision: 22
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# logical_and, struct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un objet de fonction prédéfinie qui exécute l'opération logique de conjonction \(`operator&&`\) sur ses arguments.  
  
## Syntaxe  
  
```  
template<class Type = void>  
   struct logical_and : public binary_function<Type, Type, bool>   
   {  
      bool operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator&&  
template<>  
   struct logical_and<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
         -> decltype(std::forward<Type1>(Left)  
            && std::forward<Type2>(Right));  
   };  
  
```  
  
#### Paramètres  
 `Type`, `Type1`, `Type2`  
 Tout type qui prend en charge `operator&&` qui prend des opérandes des types spécifiés ou déduits.  
  
 `Left`  
 L'opérande gauche de l'opération logique de conjonction.  Le modèle non spécialisé prend un argument de référence lvalue de type `Type`.  Le modèle spécialisé perfectionne le transfert des arguments de référence lvalue et rvalue de type déduit `Type1`.  
  
 `Right`  
 L'opérande droit de l'opération logique de conjonction.  Le modèle non spécialisé prend un argument de référence lvalue de type `Type`.  Le modèle spécialisé perfectionne le transfert des arguments de référence lvalue et rvalue de type déduit `Type2`.  
  
## Valeur de retour  
 Le résultat de `Left` \* `&&` \+ `Right`.  Le modèle spécialisé effectue de façon parfaite le transfert du résultat, qui a le type retourné par `operator&&`.  
  
## Notes  
 Pour les types définis par l'utilisateur, aucun court\-circuit d'évaluation d'opérande.  Les deux arguments sont évalués par `operator&&`.  
  
## Exemple  
  
```  
// functional_logical_and.cpp  
// compile with: /EHsc  
  
#define _CRT_RAND_S  
#include <stdlib.h>  
#include <deque>  
#include <algorithm>  
#include <functional>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   deque<bool> d1, d2, d3( 7 );  
   deque<bool>::iterator iter1, iter2, iter3;  
  
   unsigned int randomValue;  
  
   int i;  
   for ( i = 0 ; i < 7 ; i++ )  
   {  
      if ( rand_s( &randomValue ) == 0 )  
      {  
         d1.push_back((bool)(( randomValue % 2 ) != 0));  
      }  
  
   }  
  
   int j;  
   for ( j = 0 ; j < 7 ; j++ )  
   {  
      if ( rand_s( &randomValue ) == 0 )  
      {  
         d2.push_back((bool)(( randomValue % 2 ) != 0));  
      }  
   }  
  
   cout << boolalpha;    // boolalpha I/O flag on  
  
   cout << "Original deque:\n d1 = ( " ;  
   for ( iter1 = d1.begin( ) ; iter1 != d1.end( ) ; iter1++ )  
      cout << *iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "Original deque:\n d2 = ( " ;  
   for ( iter2 = d2.begin( ) ; iter2 != d2.end( ) ; iter2++ )  
      cout << *iter2 << " ";  
   cout << ")" << endl;  
  
   // To find element-wise conjunction of the truth values  
   // of d1 & d2, use the logical_and function object  
   transform( d1.begin( ), d1.end( ), d2.begin( ),  
      d3.begin( ), logical_and<bool>( ) );  
   cout << "The deque which is the conjuction of d1 & d2 is:\n d3 = ( " ;  
   for ( iter3 = d3.begin( ) ; iter3 != d3.end( ) ; iter3++ )  
      cout << *iter3 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **Deque d'origine :**  
 **d1 \= \( true true true true true false false \)**  
**Deque d'origine :**  
 **d2 \= \( true false true true false true false \)**  
**Le deque qui est le conjonction de d1 & d2 est :**  
 **d3 \= \( true false true true false false false \)**   
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)