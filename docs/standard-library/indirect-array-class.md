---
title: "indirect_array, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.indirect_array"
  - "valarray/std::indirect_array"
  - "std::indirect_array"
  - "indirect_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "indirect_array (classe)"
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# indirect_array, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe de modèle interne et connexe qui prend en charge les objets qui sont des sous\-ensembles de valarrays en fournissant des opérations entre les tables de sous\-ensemble défini en spécifiant un sous\-ensemble d'un valarray parent.  
  
## Syntaxe  
  
```  
template<class Type>  
   class indirect_array {  
public:  
   typedef Type value_type;  
   void operator=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator=(  
      const Type& x  
   ) const;  
  
   void operator*=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator/=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator%=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator+=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator-=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator^=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator&=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator|=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator<<=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator>>=(  
      const valarray<Type>& x  
   ) const;  
  
// The rest is private or implementation defined  
}  
```  
  
## Notes  
 La classe décrit un objet qui contient une référence à un objet **va** de la classe [valarray](../standard-library/valarray-class.md)**\<Type\>**, avec un objet **xa** de la classe **valarray\<size\_t\>**, qui décrit la séquence d'éléments à sélectionner depuis le **valarray\<Type\>**.  
  
 Vous construisez un objet d'**indirect\_array\<Type\>** uniquement en entrant une expression de format **va\[xa\]**.  Les fonctions membres de la classe indirect\_array se comportent ensuite comme les signatures de la fonction correspondantes définies pour **valarray\<Type\>**, mais seule la séquence d'éléments sélectionnés est affectée.  
  
 La séquence se compose des éléments de **xa.**[taille](../Topic/valarray::size.md), où l'élément `I` devient l'index **xa**\[`I`\] dans **va**.  
  
## Exemple :  
  
```  
// indirect_array.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> va ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      va [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      va [ i ] =  -1;  
  
   cout << "The initial operand valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   // Select 2nd, 4th & 6th elements  
   // and assign a value of 10 to them  
   valarray<size_t> indx ( 3 );  
   indx [0] = 2;  
   indx [1] = 4;  
   indx [2] = 6;  
   va[indx] = 10;  
  
   cout << "The modified operand valarray is:  ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
}  
```  
  
### Sortie  
  
```  
The initial operand valarray is:  ( 0 -1 2 -1 4 -1 6 -1 8 -1 ).  
The modified operand valarray is:  ( 0 -1 10 -1 10 -1 10 -1 8 -1 ).  
```  
  
## Configuration requise  
 **Header:**\<valarray\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)