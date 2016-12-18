---
title: "pair, structure | Microsoft Docs"
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
  - "utility/std::pair"
  - "pair"
  - "std::pair"
  - "std.pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pair (classe)"
ms.assetid: 539d3d67-80a2-4170-b347-783495d42109
caps.latest.revision: 20
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pair, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Struct qui offre la possibilité de traiter deux objets comme un objet unique.  
  
## Syntaxe  
  
```  
template<class T1, class T2>  
   struct pair   
   {  
   typedef T1 first_type;  
   typedef T2 second_type;  
   T1 first;  
   T2 second;  
  
   constexpr pair( );  
   constexpr pair(  
      const T1& Val1,   
      const T2& Val2  
   );  
  
   template<class Other1, class Other2>  
      constexpr pair(  
         const pair<Other1, Other2>& Right  
      );  
  
template<class Other1, class Other2>  
      constexpr pair(  
        const pair <Other1 Val1, Other2 Val2>&& Right  
      );  
  
   template<class Other1, class Other2>  
      constexpr pair(  
         Other1&& Val1, Other2&& Val2  
      );  
   };  
```  
  
#### Paramètres  
 `Val1`  
 Valeur initialisant le premier élément de `pair`.  
  
 `Val2`  
 Valeur initialisant le second élément de `pair`.  
  
 `Right`  
 Paire dont les valeurs doivent être utilisées pour initialiser les éléments d'une autre paire.  
  
## Valeur de retour  
 Le premier constructeur \(par défaut\) initialise le premier élément de la paire à la valeur par défaut de type **T1** et le second élément à la valeur par défaut de type **T2**.  
  
 Le deuxième constructeur initialise le premier élément de la paire à `Val1` et le deuxième élément à *Val2*.  
  
 Le troisième constructeur \(modèle\) initialise le premier élément de la paire à `Right`.**first** et le deuxième élément à `Right`.**second**.  
  
 Le quatrième constructeur initialise le premier élément de la paire à `Val1` et le deuxième élément à *Val2* à l'aide de [Déclarateur de référence Rvalue : &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## Notes  
 La structure de modèle stocke une paire d'objets respectivement de type **T1** et **T2**.  Le type **first\_type** est identique au paramètre de modèle **T1** et le type **second\_type** est identique au paramètre de modèle **T2**.  **T1** et **T2** doivent chacun fournir uniquement un constructeur par défaut, un constructeur à argument unique et un destructeur.  Tous les membres du type `pair` sont publics, car le type est déclaré comme un `struct` plutôt que comme une **classe**.  Les deux utilisations les plus courantes pour une paire sont en tant que types de retour pour des fonctions qui retournent deux valeurs et en tant qu'éléments pour les classes de conteneurs associatifs \([classe map](../standard-library/map-class.md) et [classe multimap](../standard-library/multimap-class.md)\) qui ont à la fois une clé et un type de valeur associés à chaque élément.  Cette dernière satisfait à l'exigence relative à un conteneur associatif de paires et a un type de valeur de la forme `pair`\<**const** `key_type`, `mapped_type`\>.  
  
## Exemple  
  
```  
// utility_pair.cpp  
// compile with: /EHsc  
#include <utility>  
#include <map>  
#include <iomanip>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Using the constructor to declare and initialize a pair  
   pair <int, double> p1 ( 10, 1.1e-2 );  
  
   // Compare using the helper function to declare and initialize a pair  
   pair <int, double> p2;  
   p2 = make_pair ( 10, 2.22e-1 );  
  
   // Making a copy of a pair  
   pair <int, double> p3 ( p1 );  
  
   cout.precision ( 3 );  
   cout << "The pair p1 is: ( " << p1.first << ", "   
        << p1.second << " )." << endl;  
   cout << "The pair p2 is: ( " << p2.first << ", "   
        << p2.second << " )." << endl;  
   cout << "The pair p3 is: ( " << p3.first << ", "   
        << p3.second << " )." << endl;  
  
   // Using a pair for a map element  
   map <int, int> m1;  
   map <int, int>::iterator m1_Iter;  
  
   typedef pair <int, int> Map_Int_Pair;  
  
   m1.insert ( Map_Int_Pair ( 1, 10 ) );  
   m1.insert ( Map_Int_Pair ( 2, 20 ) );  
   m1.insert ( Map_Int_Pair ( 3, 30 ) );  
  
   cout << "The element pairs of the map m1 are:";  
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )  
      cout << " ( " << m1_Iter -> first << ", "  
           << m1_Iter -> second << " )";  
   cout   << "." << endl;  
  
   // Using pair as a return type for a function  
   pair< map<int,int>::iterator, bool > pr1, pr2;  
   pr1 = m1.insert ( Map_Int_Pair ( 4, 40 ) );  
   pr2 = m1.insert ( Map_Int_Pair (1, 10 ) );  
  
   if( pr1.second == true )  
   {  
      cout << "The element (4,40) was inserted successfully in m1."  
           << endl;  
   }  
   else     
   {  
      cout << "The element with a key value of\n"  
           << " ( (pr1.first) -> first ) = " << ( pr1.first ) -> first   
           << " is already in m1,\n so the insertion failed." << endl;  
   }  
  
   if( pr2.second == true )  
   {  
      cout << "The element (1,10) was inserted successfully in m1."  
           << endl;  
   }  
   else     
   {  
      cout << "The element with a key value of\n"  
           << " ( (pr2.first) -> first ) = " << ( pr2.first ) -> first   
           << " is already in m1,\n so the insertion failed." << endl;  
   }  
}  
```  
  
  **The pair p1 is: \( 10, 0.011 \).  The pair p2 is: \( 10, 0.222 \).  The pair p3 is: \( 10, 0.011 \).  The element pairs of the map m1 are: \( 1, 10 \) \( 2, 20 \) \( 3, 30 \).  The element \(4,40\) was inserted successfully in m1.  The element with a key value of**  
 **\( \(pr2.first\) \-\> first \) \= 1 is already in m1,**  
 **so the insertion failed.**    
## Configuration requise  
 **En\-tête :** \<utility\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [pair, opérateur logique](../misc/pair-logical-operator.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)