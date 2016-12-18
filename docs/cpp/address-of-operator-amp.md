---
title: "Op&#233;rateur address-of&#160;: &amp; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "address-of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& (opérateur)"
  - "& (opérateur), address-of (opérateur)"
  - "address-of (opérateur) (&)"
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateur address-of&#160;: &amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
& cast-expression  
```  
  
## Notes  
 L'opérateur d'adresse unaire \(**&**\) prend l'adresse de son opérande.  L'opérande de l'opérateur d'adresse peut être un désignateur de fonction ou une l\-value qui désigne un objet qui n'est pas un champ de bits et n'est pas déclaré avec le spécificateur de classe de stockage **register**.  
  
 L'opérateur d'adresse peut être appliqué uniquement aux variables dotées de types fondamentaux, de structure, de classe ou d'union qui sont déclarées au niveau de la portée du fichier, ou aux références indicées de tableau.  Dans ces expressions, une expression constante qui n'inclut pas l'opérateur d'adresse peut être ajoutée ou soustraite dans l'expression d'adresse.  
  
 Lorsqu'il est appliqué à des fonctions ou des l\-values, le résultat de l'expression est un type pointeur \(une r\-value\) dérivé du type de l'opérande.  Par exemple, si l'opérande est de type `char`, le résultat de l'expression est de type pointeur vers `char`.  L'opérateur d'adresse, appliqué à des objets **const** ou `volatile`, correspond à **const** `type` **\*** ou `volatile` `type` **\***, où `type` est le type de l'objet d'origine.  
  
 Lorsque l'opérateur d'adresse est appliqué à un [nom qualifié](http://msdn.microsoft.com/fr-fr/3fefb16d-8120-4627-8b3f-3d90fbdcd1df), le résultat varie selon que le *qualified\-name* spécifie ou non un membre statique.  Si oui, le résultat est un pointeur vers le type spécifié dans la déclaration du membre.  Si le membre n'est pas statique, le résultat est un pointeur vers le *nom* du membre de la classe indiquée par *qualified\-class\-name*. \(Consultez [Expressions primaires](../cpp/primary-expressions.md) pour plus d'informations sur *qualified\-class\-name*.\) Le fragment de code ci\-dessous montre comment le résultat diffère si le membre est statique ou non :  
  
```  
// expre_Address_Of_Operator.cpp  
// C2440 expected  
class PTM {  
public:  
           int   iValue;  
    static float fValue;  
};  
  
int main() {  
   int   PTM::*piValue = &PTM::iValue;  // OK: non-static  
   float PTM::*pfValue = &PTM::fValue;  // C2440 error: static  
   float *spfValue     = &PTM::fValue;  // OK  
}  
```  
  
 Dans cet exemple, l'expression `&PTM::fValue` permet d'obtenir le type `float *` à la place du type `float PTM::*`, car `fValue` est un membre statique.  
  
 L'adresse d'une fonction surchargée peut être prise uniquement lorsque vous savez clairement quelle version de la fonction est référencée.  Consultez [Adresse des fonctions surchargées](../misc/address-of-overloaded-functions.md) pour plus d'informations sur la façon d'obtenir l'adresse d'une fonction surchargée spécifique.  
  
 L'application de l'opérateur d'adresse à un type référence fournit le même résultat que l'application de l'opérateur à l'objet auquel la référence est liée.  Par exemple :  
  
## Exemple  
  
```  
// expre_Address_Of_Operator2.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main() {  
   double d;        // Define an object of type double.  
   double& rd = d;  // Define a reference to the object.  
  
   // Obtain and compare their addresses  
   if( &d == &rd )  
      cout << "&d equals &rd" << endl;  
}  
```  
  
## Sortie  
  
```  
&d equals &rd  
```  
  
 L'exemple ci\-dessous utilise l'opérateur d'adresse pour passer un argument de pointeur à une fonction :  
  
```  
// expre_Address_Of_Operator3.cpp  
// compile with: /EHsc  
// Demonstrate address-of operator &  
  
#include <iostream>  
using namespace std;  
  
// Function argument is pointer to type int  
int square( int *n ) {  
   return (*n) * (*n);  
}  
  
int main() {  
   int mynum = 5;  
   cout << square( &mynum ) << endl;   // pass address of int  
}  
```  
  
## Sortie  
  
```  
25  
```  
  
## Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Déclarateur de référence Lvalue : &](../cpp/lvalue-reference-declarator-amp.md)   
 [Indirection et opérateurs d'adresse](../c-language/indirection-and-address-of-operators.md)