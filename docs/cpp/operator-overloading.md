---
title: "Surcharge d’opérateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- operator_cpp
- operator
dev_langs:
- C++
helpviewer_keywords:
- redefinable operators
- non-redefinable operators
- operator keyword [C++]
- operators [C++], overloading
- operator overloading
ms.assetid: 56ad4c4f-dd0c-45e0-adaa-08fe98cb1f8e
caps.latest.revision: 13
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
ms.openlocfilehash: 5ac9415ec186760a70394772ffaff011d7c68c95
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="operator-overloading"></a>Surcharge d'opérateur
Le mot clé `operator` déclare une fonction spécifiant la signification de `operator-symbol` quand il est appliqué aux instances d'une classe. Cela donne à l'opérateur plusieurs significations ou le « surcharge ». Le compilateur fait la distinction entre les différentes significations d’un opérateur en examinant les types de ses opérandes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
type operator operator-symbol ( parameter-list )  
```  
  
## <a name="remarks"></a>Remarques  
 Vous pouvez redéfinir la fonction de la plupart des opérateurs intégrés de manière globale ou classe par classe. Les opérateurs surchargés sont implémentés en tant que fonctions.  
  
 Le nom d’un opérateur surchargé est `operator x`, où `x` est l’opérateur tel qu’il apparaît dans le tableau suivant. Par exemple, pour surcharger l'opérateur d'addition, vous définissez une fonction appelée `operator+`. De la même façon, pour surcharger l'opérateur d'addition/assignation, `+=`, vous définissez une fonction appelée `operator+=`.  
  
### <a name="redefinable-operators"></a>Opérateurs redéfinissables  
  
|Opérateur|Nom|Type|  
|--------------|----------|----------|  
|`,`|Virgule|Binaire|  
|`!`|NOT logique|Unaire|  
|`!=`|Inégalité|Binaire|  
|`%`|Modulo|Binaire|  
|`%=`|Assignation de modulo|Binaire|  
|`&`|Opération de bits AND|Binaire|  
|`&`|Adresse-de|Unaire|  
|`&&`|AND logique|Binaire|  
|`&=`|Assignation d'opération AND au niveau du bit|Binaire|  
|`( )`|Appel de fonction |—|  
|`( )`|Opérateur de cast|Unaire|  
|`*`|Multiplication|Binaire|  
|`*`|Déréférencement du pointeur|Unaire|  
|`*=`|Assignation de multiplication|Binaire|  
|`+`|Addition|Binaire|  
|`+`|Plus unaire|Unaire|  
|`++`|Incrément <sup>1</sup>|Unaire|  
|`+=`|Assignation d'addition|Binaire|  
|`-`|Soustraction|Binaire|  
|`-`|Négation unaire|Unaire|  
|`--`|Décrément <sup>1</sup>|Unaire|  
|`-=`|Assignation de soustraction|Binaire|  
|`->`|Sélection de membres|Binaire|  
|`->*`|Sélection de pointeur de membre|Binaire|  
|`/`|Division|Binaire|  
|`/=`|Assignation de division|Binaire|  
|`<`|Inférieur à|Binaire|  
|`<<`|Décalage vers la gauche|Binaire|  
|`<<=`|Assignation de décalage vers la gauche|Binaire|  
|`<=`|Inférieur ou égal à|Binaire|  
|`=`|Assignation|Binaire|  
|`==`|Égalité|Binaire|  
|`>`|Supérieur à|Binaire|  
|`>=`|Supérieur ou égal à|Binaire|  
|`>>`|Décalage vers la droite|Binaire|  
|`>>=`|Assignation de décalage vers la droite|Binaire|  
|`[ ]`|Indice de tableau|—|  
|`^`|OR exclusive|Binaire|  
|`^=`|Assignation OR exclusive|Binaire|  
|`&#124;`|Opération de bits OR inclusive|Binaire|  
|`&#124;=`|Assignation d'opération OR inclusive au niveau du bit|Binaire|  
|`&#124;&#124;`|OR logique|Binaire|  
|`~`|Complément à 1|Unaire|  
|`delete`|`Delete`|—|  
|`new`|`New`|—|  
|`conversion operators`|opérateurs de conversion|Unaire|  
  
 1 deux versions de l’unaire incrémentent et opérateurs de décrément existent : préincrément et postincrément.  
  
 Consultez [règles générales pour la surcharge d’opérateur](../cpp/general-rules-for-operator-overloading.md) pour plus d’informations. Les contraintes sur les différentes catégories d'opérateurs surchargés sont décrites dans les rubriques suivantes :  
  
-   [Opérateurs unaires](../cpp/overloading-unary-operators.md)  
  
-   [Opérateurs binaires](../cpp/binary-operators.md)  
  
-   [Attribution](../cpp/assignment.md)  
  
-   [Appel de fonction](../cpp/function-call-cpp.md)  
  
-   [Indices](../cpp/subscripting.md)  
  
-   [Accès aux membres de classe](../cpp/member-access.md)  
  
-   [Incrémentation et décrémentation](../cpp/increment-and-decrement-operator-overloading-cpp.md).  
  
-   [Conversions de Type défini par l’utilisateur](../cpp/user-defined-type-conversions-cpp.md)  
  
 Les opérateurs indiqués dans le tableau suivant ne peuvent pas être surchargés. Le tableau inclut les symboles de préprocesseur `#` et `##`.  
  
### <a name="nonredefinable-operators"></a>Opérateurs non redéfinissables  
  
|||  
|-|-|  
|`Operator`|`Name`|  
|`.`|Sélection de membres|  
|`.*`|Sélection de pointeur de membre|  
|`::`|Résolution de portée|  
|`? :`|Conditionnel|  
|`#`|Préprocesseur convertir en type string|  
|`##`|Préprocesseur concaténer|  
  
 Bien que les opérateurs surchargés soient généralement appelés implicitement par le compilateur quand ils sont trouvés dans le code, ils peuvent être invoqués explicitement de la même façon que n'importe quelle fonction membre ou non membre :  
  
```  
Point pt;  
pt.operator+( 3 );  // Call addition operator to add 3 to pt.  
```  
  
## <a name="example"></a>Exemple  
 L'exemple suivant surcharge l'opérateur `+` pour additionner deux nombres complexes et retourne le résultat.  
  
```  
// operator_overloading.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct Complex {  
   Complex( double r, double i ) : re(r), im(i) {}  
   Complex operator+( Complex &other );  
   void Display( ) {   cout << re << ", " << im << endl; }  
private:  
   double re, im;  
};  
  
// Operator overloaded using a member function  
Complex Complex::operator+( Complex &other ) {  
   return Complex( re + other.re, im + other.im );  
}  
  
int main() {  
   Complex a = Complex( 1.2, 3.4 );  
   Complex b = Complex( 5.6, 7.8 );  
   Complex c = Complex( 0.0, 0.0 );  
  
   c = a + b;  
   c.Display();  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
6.8, 11.2  
```  
  
## <a name="in-this-section"></a>Dans cette section  
  
1.  [Règles générales de surcharge d’opérateur](../cpp/general-rules-for-operator-overloading.md)  
  
2.  [Surcharge des opérateurs unaires](../cpp/overloading-unary-operators.md)  
  
3.  [Opérateurs binaires](../cpp/binary-operators.md)  
  
4.  [Attribution](../cpp/assignment.md)  
  
5.  [Appel de fonction](../cpp/function-call-cpp.md)  
  
6.  [Indices](../cpp/subscripting.md)  
  
7.  [Accès au membre](../cpp/member-access.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Les opérateurs C++ intégrés, priorité et associativité](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Mots clés](../cpp/keywords-cpp.md)
