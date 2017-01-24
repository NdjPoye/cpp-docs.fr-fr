---
title: "Mise en indice | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tableaux (C++), mettre en indice"
  - "surcharge d'opérateur, exemples"
  - "opérateurs (C++), surcharger"
  - "opérateur d'indice"
  - "opérateur d'indice, surchargés"
  - "mettre en indice"
ms.assetid: eb151281-6733-401d-9787-39ab6754c62c
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mise en indice
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'opérateur d'indice \(**\[ \]**\), comme l'opérateur d'appel de fonction, est considéré comme un opérateur binaire.  L'opérateur d'indice doit être une fonction membre non statique qui accepte un seul argument.  Cet argument peut être de tout type et désigne l'indice de tableau souhaité.  
  
## Exemple  
 L'exemple suivant montre comment créer un vecteur de type `int` qui implémente la vérification des limites :  
  
```  
// subscripting.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class IntVector {  
public:  
   IntVector( int cElements );  
   ~IntVector() { delete [] _iElements; }  
   int& operator[](int nSubscript);  
private:  
   int *_iElements;  
   int _iUpperBound;  
};  
  
// Construct an IntVector.  
IntVector::IntVector( int cElements ) {  
   _iElements = new int[cElements];  
   _iUpperBound = cElements;  
}  
  
// Subscript operator for IntVector.  
int& IntVector::operator[](int nSubscript) {  
   static int iErr = -1;  
  
   if( nSubscript >= 0 && nSubscript < _iUpperBound )  
      return _iElements[nSubscript];  
   else {  
      clog << "Array bounds violation." << endl;  
      return iErr;  
   }  
}  
  
// Test the IntVector class.  
int main() {  
   IntVector v( 10 );  
   int i;  
  
   for( i = 0; i <= 10; ++i )  
      v[i] = i;  
  
   v[3] = v[9];  
  
   for ( i = 0; i <= 10; ++i )  
      cout << "Element: [" << i << "] = " << v[i] << endl;  
}  
```  
  
  **Violation de limites de tableau.**  
**Élément : \[0\] \= 0**  
**Élément : \[1\] \= 1**  
**Élément : \[2\] \= 2**  
**Élément : \[3\] \= 9**  
**Élément : \[4\] \= 4**  
**Élément : \[5\] \= 5**  
**Élément : \[6\] \= 6**  
**Élément : \[7\] \= 7**  
**Élément : \[8\] \= 8**  
**Élément : \[9\] \= 9**  
**Violation de limites de tableau.**  
**Élément : \[10\] \= 10**   
## Commentaires  
 Lorsque `i` atteint 10 dans le programme précédent, `operator[]` détecte qu'un indice hors limite est utilisé et émet un message d'erreur.  
  
 Notez que la fonction `operator[]` retourne un type référence.  Il s'agit par conséquent d'une l\-value, ce qui vous permet d'utiliser des expressions indicées de chaque côté des opérateurs d'assignation.  
  
## Voir aussi  
 [Surcharge d'opérateur](../cpp/operator-overloading.md)