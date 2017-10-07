---
title: "Opérateur const_cast | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- const_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 8f72367cb4970b2ce0121efc43b79691155808df
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="constcast-operator"></a>const_cast, opérateur
Supprime la **const**, `volatile`, et **__unaligned** ou les attributs d’une classe.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
const_cast <   
type-id  
 > (   
expression  
 )  
  
```  
  
## <a name="remarks"></a>Remarques  
 Un pointeur vers n’importe quel type d’objet ou un pointeur vers un membre de données peut être explicitement converti en un type qui est identique à l’exception de la **const**, `volatile`, et **__unaligned** qualificateurs. Pour les pointeurs et des références, le résultat fait référence à l'objet d'origine. Pour les pointeurs vers des données membres, le résultat fait référence au même membre que le pointeur d'origine (sans cast) vers les données membres. Selon le type de l'objet référencé, une opération d'écriture via le pointeur résultant, la référence, ou le pointeur vers les données membres peut entraîner un comportement non défini.  
  
 Vous ne pouvez pas utiliser l'opérateur `const_cast` pour substituer directement l'état constant d'une variable constante.  
  
 L'opérateur `const_cast` convertit une valeur de pointeur null en la valeur de pointeur null du type de destination.  
  
## <a name="example"></a>Exemple  
  
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
  
 Sur la ligne contenant `const_cast`, le type de données du pointeur `this` est `const CCTest *`. L'opérateur `const_cast` remplace le type de données du pointeur `this` par `CCTest *` en autorisant la modification du membre `number`. Le cast dure uniquement pendant le reste de l'instruction dans laquelle il apparaît.  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateurs de casting](../cpp/casting-operators.md)   
 [Mots clés](../cpp/keywords-cpp.md)
