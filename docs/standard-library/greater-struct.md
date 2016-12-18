---
title: "greater, struct | Microsoft Docs"
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
  - "greater"
  - "xfunctional/std::greater"
  - "std.greater"
  - "std::greater"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "greater (struct)"
  - "greater (fonction)"
ms.assetid: ebc348e1-edcd-466b-b21a-db95bd8f9079
caps.latest.revision: 22
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# greater, struct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un prédicat binaire qui exécute l'opération supérieur\-à \(`operator>`\) à ses arguments.  
  
## Syntaxe  
  
```  
template<class Type = void>  
   struct greater : public binary_function <Type, Type, bool>   
   {  
      bool operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator>  
template<>  
   struct greater<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
      -> decltype(std::forward<Type1>(Left)  
         > std::forward<Type2>(Right));  
   };  
  
```  
  
#### Paramètres  
 `Type`, `Type1`, `Type2`  
 Tout type qui prend en charge `operator>` qui prend des opérandes des types spécifiés ou déduits.  
  
 `Left`  
 L'opérande de gauche de l'opération supérieur\-à.  Le modèle non spécialisé prend un argument de référence lvalue de type `Type`.  Le modèle spécialisé perfectionne le transfert des arguments de référence lvalue et rvalue de type déduit `Type1`.  
  
 `Right`  
 L'opérande de droite de l'opération supérieur\-à.  Le modèle non spécialisé prend un argument de référence lvalue de type `Type`.  Le modèle spécialisé perfectionne le transfert des arguments de référence lvalue et rvalue de type déduit `Type2`.  
  
## Valeur de retour  
 Le résultat de `Left` \* `>` \+ `Right`.  Le modèle spécialisé effectue de façon parfaite le transfert du résultat, qui a le type retourné par `operator>`.  
  
## Notes  
 Le prédicat binaire `greater`\<`Type`\> fournit une commande faible stricte d'un ensemble de valeurs d'éléments de type `Type` dans les classes d'équivalence, si et seulement si ce type satisfait aux exigences mathématiques standard pour être classée.  Les spécialisations pour tout type de pointeur produisent une commande globale d'éléments, car tous les éléments des valeurs distinctes sont classés par rapport à l'autre.  
  
## Exemple  
  
```  
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
  
## Sortie  
  
```  
Original vector v1 = ( 41 18467 6334 26500 19169 15724 11478 29358 )  
Sorted vector v1 = ( 41 6334 11478 15724 18467 19169 26500 29358 )  
Resorted vector v1 = ( 29358 26500 19169 18467 15724 11478 6334 41 )  
```  
  
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)