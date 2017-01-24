---
title: "const_cast, op&#233;rateur | Microsoft Docs"
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
  - "const_cast"
  - "const_cast_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_cast (mot clé) (C++)"
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# const_cast, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Supprime les attributs **const**, `volatile` et **\_\_unaligned** d'une classe.  
  
## Syntaxe  
  
```  
  
const_cast <   
type-id  
 > (   
expression  
 )  
  
```  
  
## Notes  
 Un pointeur vers tout type d'objet ou un pointeur vers une donnée membre peut être converti explicitement en un type identique, sauf pour les qualificateurs **const**, `volatile` et **\_\_unaligned**.  Pour les pointeurs et des références, le résultat fait référence à l'objet d'origine.  Pour les pointeurs vers des données membres, le résultat fait référence au même membre que le pointeur d'origine \(sans cast\) vers les données membres.  Selon le type de l'objet référencé, une opération d'écriture via le pointeur résultant, la référence, ou le pointeur vers les données membres peut entraîner un comportement non défini.  
  
 Vous ne pouvez pas utiliser l'opérateur `const_cast` pour substituer directement l'état constant d'une variable constante.  
  
 L'opérateur `const_cast` convertit une valeur de pointeur null en la valeur de pointeur null du type de destination.  
  
## Exemple  
  
```  
// expre_const_cast_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class CCTest {  
public:  
   void setNumber( int );  
   void printNumber() const;  
private:  
   int number;  
};  
  
void CCTest::setNumber( int num ) { number = num; }  
  
void CCTest::printNumber() const {  
   cout << "\nBefore: " << number;  
   const_cast< CCTest * >( this )->number--;  
   cout << "\nAfter: " << number;  
}  
  
int main() {  
   CCTest X;  
   X.setNumber( 8 );  
   X.printNumber();  
}  
```  
  
 Sur la ligne contenant `const_cast`, le type de données du pointeur `this` est `const CCTest *`.  L'opérateur `const_cast` remplace le type de données du pointeur `this` par `CCTest *` en autorisant la modification du membre `number`.  Le cast dure uniquement pendant le reste de l'instruction dans laquelle il apparaît.  
  
## Voir aussi  
 [Opérateurs de casting](../cpp/casting-operators.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)