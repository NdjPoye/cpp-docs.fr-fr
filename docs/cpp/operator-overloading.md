---
title: "Surcharge d&#39;op&#233;rateur | Microsoft Docs"
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
  - "operator_cpp"
  - "operator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opérateurs non redéfinissables"
  - "operator (mot clé) (C++)"
  - "surcharge d'opérateur"
  - "opérateurs (C++), surcharger"
  - "opérateurs redéfinissables"
ms.assetid: 56ad4c4f-dd0c-45e0-adaa-08fe98cb1f8e
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Surcharge d&#39;op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le mot clé `operator` déclare une fonction spécifiant la signification de `operator-symbol` quand il est appliqué aux instances d'une classe.  Cela donne à l'opérateur plusieurs significations ou le « surcharge ».  Le compilateur fait la distinction entre les différentes significations d'un opérateur en examinant les types de ses opérandes.  
  
## Syntaxe  
  
```  
  
type operator operator-symbol ( parameter-list )  
```  
  
## Notes  
 Vous pouvez redéfinir la fonction de la plupart des opérateurs intégrés de manière globale ou classe par classe.  Les opérateurs surchargés sont implémentés en tant que fonctions.  
  
 Le nom d'un opérateur surchargé est `operator``x`, où `x` désigne l'opérateur tel qu'il apparaît dans le tableau suivant.  Par exemple, pour surcharger l'opérateur d'addition, vous définissez une fonction appelée `operator+`.  De la même façon, pour surcharger l'opérateur d'addition\/assignation, `+=`, vous définissez une fonction appelée `operator+=`.  
  
### Opérateurs redéfinissables  
  
|Opérateur|Nom|Type|  
|---------------|---------|----------|  
|`,`|Virgule|Binaire|  
|`!`|NOT logique|Unaire|  
|`!=`|Inégalité|Binaire|  
|`%`|Modulo|Binaire|  
|`%=`|Assignation de modulo|Binaire|  
|`&`|Opération de bits AND|Binaire|  
|`&`|Adresse\-de|Unaire|  
|`&&`|AND logique|Binaire|  
|`&=`|Assignation d'opération AND au niveau du bit|Binaire|  
|`( )`|Appel de fonction|—|  
|`( )`|Opérateur de cast|Unaire|  
|`*`|Multiplication|Binaire|  
|`*`|Déréférencement du pointeur|Unaire|  
|`*=`|Assignation de multiplication|Binaire|  
|`+`|Addition|Binaire|  
|`+`|Plus unaire|Unaire|  
|`++`|Incrément <sup>1</sup>|Unaire|  
|`+=`|Assignation d'addition|Binaire|  
|`–`|Soustraction|Binaire|  
|`–`|Négation unaire|Unaire|  
|`––`|Décrément <sup>1</sup>|Unaire|  
|`–=`|Assignation de soustraction|Binaire|  
|`–>`|Sélection de membres|Binaire|  
|`–>*`|Sélection de pointeur de membre|Binaire|  
|`/`|Division|Binaire|  
|`/=`|Assignation de division|Binaire|  
|`<`|Inférieur à|Binaire|  
|`<<`|Décalage vers la gauche|Binaire|  
|`<<=`|Assignation de décalage vers la gauche|Binaire|  
|`<=`|Inférieur ou égal à|Binaire|  
|`=`|Attribution|Binaire|  
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
  
 1   Il existe deux versions des opérateurs d'incrémentation et de décrémentation unaire : préincrément et postincrément.  
  
 Voir [Règles générales pour la surcharge d'opérateur](../cpp/general-rules-for-operator-overloading.md) pour plus d'informations.  Les contraintes sur les différentes catégories d'opérateurs surchargés sont décrites dans les rubriques suivantes :  
  
-   [Opérateurs unaires](../cpp/overloading-unary-operators.md)  
  
-   [Opérateurs binaires](../cpp/binary-operators.md)  
  
-   [Attribution](../cpp/assignment.md)  
  
-   [Appel de fonction](../cpp/function-call-cpp.md)  
  
-   [Indices](../cpp/subscripting.md)  
  
-   [Accès aux membres de la classe](../cpp/member-access.md)  
  
-   [Incrément et décrément](../cpp/increment-and-decrement-operator-overloading-cpp.md).  
  
-   [Conversions](../cpp/user-defined-type-conversions-cpp.md)  
  
 Les opérateurs indiqués dans le tableau suivant ne peuvent pas être surchargés.  Le tableau inclut les symboles de préprocesseur `#` et `##`.  
  
### Opérateurs non redéfinissables  
  
|||  
|-|-|  
|`Operator`|`Name`|  
|`.`|Sélection de membres|  
|`.*`|Sélection de pointeur de membre|  
|`::`|Résolution de portée|  
|`?  :`|Conditionnel|  
|`#`|Préprocesseur convertir en type string|  
|`##`|Préprocesseur concaténer|  
  
 Bien que les opérateurs surchargés soient généralement appelés implicitement par le compilateur quand ils sont trouvés dans le code, ils peuvent être invoqués explicitement de la même façon que n'importe quelle fonction membre ou non membre :  
  
```  
Point pt;  
pt.operator+( 3 );  // Call addition operator to add 3 to pt.  
```  
  
## Exemple  
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
  
## Sortie  
  
```  
6.8, 11.2  
```  
  
## Dans cette section  
  
1.  [Règles générales de surcharge d'opérateur](../cpp/general-rules-for-operator-overloading.md)  
  
2.  [Surcharge des opérateurs unaires](../cpp/overloading-unary-operators.md)  
  
3.  [Opérateurs binaires](../cpp/binary-operators.md)  
  
4.  [Assignation](../cpp/assignment.md)  
  
5.  [Appel de fonction](../cpp/function-call-cpp.md)  
  
6.  [Mise en indice](../cpp/subscripting.md)  
  
7.  [Accès aux membres](../cpp/member-access.md)  
  
## Voir aussi  
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)