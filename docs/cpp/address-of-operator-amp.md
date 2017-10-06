---
title: "Opérateur address-of : &amp; | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '&'
dev_langs:
- C++
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator, address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 56e2606759cc381c1ae6f6f4f1f7cbc1d9d2d810
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="address-of-operator-amp"></a>Opérateur address-of :&amp;
## <a name="syntax"></a>Syntaxe  
  
```  
& cast-expression  
```  
  
## <a name="remarks"></a>Remarques  
 L’opérateur d’adresse unaire (**&**) prend l’adresse de son opérande. L’opérande de l’opérateur d’adresse peut être un désignateur de fonction ou une l-value qui désigne un objet qui n’est pas un champ de bits et n’est pas déclaré avec le spécificateur de classe de stockage **register**.  
  
 L’opérateur d’adresse peut être appliqué uniquement aux variables dotées de types fondamentaux, structure, classe ou union qui sont déclarées au niveau de la portée du fichier, ou aux références indicées de tableau. Dans ces expressions, une expression constante qui n'inclut pas l'opérateur d'adresse peut être ajoutée ou soustraite dans l'expression d'adresse.  
  
 Lorsqu'il est appliqué à des fonctions ou des l-values, le résultat de l'expression est un type pointeur (une r-value) dérivé du type de l'opérande. Par exemple, si l'opérande est de type `char`, le résultat de l'expression est de type pointeur vers `char`. L’opérateur d’adresse, appliqué à **const** ou `volatile` objets, la valeur de **const** `type` ** \* ** ou `volatile` `type` ** \* **, où `type` est le type de l’objet d’origine.  
  
 Quand l’opérateur d’adresse est appliqué à un [nom qualifié](http://msdn.microsoft.com/en-us/3fefb16d-8120-4627-8b3f-3d90fbdcd1df), le résultat varie selon que le *nom qualifié* spécifie un membre statique. Si oui, le résultat est un pointeur vers le type spécifié dans la déclaration du membre. Si le membre n’est pas statique, le résultat est un pointeur vers le membre *nom* de la classe indiquée par *qualified-class-name*. (Consultez [Expressions primaires](../cpp/primary-expressions.md) pour plus d’informations *qualified-class-name*.) Le fragment de code ci-dessous montre comment le résultat diffère si le membre est statique ou non :  
  
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
  
 L'adresse d'une fonction surchargée peut être prise uniquement lorsque vous savez clairement quelle version de la fonction est référencée. Consultez [surcharge de fonction](function-overloading.md) pour plus d’informations sur la façon d’obtenir l’adresse d’un particulier de la fonction surchargée.  
  
 L'application de l'opérateur d'adresse à un type référence fournit le même résultat que l'application de l'opérateur à l'objet auquel la référence est liée. Exemple :  
  
## <a name="example"></a>Exemple  
  
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
  
## <a name="output"></a>Sortie  
  
```  
&d equals &rd  
```  
  
 L'exemple ci-dessous utilise l'opérateur d'adresse pour passer un argument de pointeur à une fonction :  
  
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
  
## <a name="output"></a>Sortie  
  
```  
25  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Les opérateurs C++ intégrés, priorité et associativité](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Déclarateur de référence lvalue : &](../cpp/lvalue-reference-declarator-amp.md)   
 [Opérateurs d’indirection et d’adresse](../c-language/indirection-and-address-of-operators.md)

