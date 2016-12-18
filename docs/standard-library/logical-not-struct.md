---
title: "logical_not, struct | Microsoft Docs"
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
  - "std.logical_not"
  - "logical_not"
  - "xfunctional/std::logical_not"
  - "std::logical_not"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "logical_not (classe)"
  - "logical_not (struct)"
ms.assetid: 892db678-31da-4540-974b-17b05efc0849
caps.latest.revision: 21
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# logical_not, struct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un objet de fonction prédéfinie qui exécute l'opération logique non \(`operator!`\) à son argument.  
  
## Syntaxe  
  
```  
template<class Type = void>  
   struct logical_not : public unary_function<Type, bool>   
   {  
      bool operator()(  
         const Type& Left  
      ) const;  
   };  
  
// specialized transparent functor for operator!  
template<>  
   struct logical_not<void>  
   {  
      template<class Type>  
      auto operator()(Type&& Left) const  
         -> decltype(!std::forward<Type>(Left));  
   };  
  
```  
  
#### Paramètres  
 `Type`  
 Tout type qui prend en charge `operator!` qui prend un opérande de type spécifié ou déduit.  
  
 `Left`  
 L'opérande de l'opérateur NOT logique.  Le modèle non spécialisé prend un argument de référence lvalue de type `Type`.  Le modèle spécialisé perfectionne le transfert des arguments de référence lvalue et rvalue de type déduit `Type`.  
  
## Valeur de retour  
 Le résultat de `!` \* `Left` \+ .  Le modèle spécialisé effectue de façon parfaite le transfert du résultat, qui a le type retourné par `operator!`.  
  
## Exemple  
  
```  
// functional_logical_not.cpp  
// compile with: /EHsc  
#include <deque>  
#include <algorithm>  
#include <functional>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   deque<bool> d1, d2 ( 7 );  
   deque<bool>::iterator iter1, iter2;  
  
   int i;  
   for ( i = 0 ; i < 7 ; i++ )  
   {  
      d1.push_back((bool)((i % 2) != 0));  
   }  
  
   cout << boolalpha;    // boolalpha I/O flag on  
  
   cout << "Original deque:\n d1 = ( " ;  
   for ( iter1 = d1.begin( ) ; iter1 != d1.end( ) ; iter1++ )  
      cout << *iter1 << " ";  
   cout << ")" << endl;  
  
   // To flip all the truth values of the elements,  
   // use the logical_not function object  
   transform( d1.begin( ), d1.end( ), d2.begin( ),logical_not<bool>( ) );  
   cout << "The deque with its values negated is:\n d2 = ( " ;  
   for ( iter2 = d2.begin( ) ; iter2 != d2.end( ) ; iter2++ )  
      cout << *iter2 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **Deque d'origine :**  
 **d1 \= \( false true false true false true false \)**  
**Le deque avec ses valeurs négative est :**  
 **d2 \= \( true false true false true false true \)**   
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)