---
title: "Opérateur de bits AND : &amp; | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bitand
- '&'
dev_langs:
- C++
helpviewer_keywords:
- AND operator
- bitwise operators, AND operator
- '& operator, bitwise operators'
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
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
ms.openlocfilehash: 99ff65f38abf5cfcac135e2cc54e3df6df5f336d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="bitwise-and-operator-amp"></a>Opérateur de bits AND :&amp;
## <a name="syntax"></a>Syntaxe  
  
```  
  
expression   
&  
 expression  
  
```  
  
## <a name="remarks"></a>Remarques  
 Les expressions peuvent être d'autres expressions-et, ou (en fonction des restrictions de type indiquées ci-dessous) des expressions d'égalité, des expressions relationnelles, des expressions additives, des expressions multiplicatives, des expressions de pointeur vers membre, des expressions de casts, des expressions unaires, des expressions suffixées ou des expressions primaires.  
  
 L’opérateur AND au niveau du bit (**&**) compare chaque bit du premier opérande au bit correspondant du second opérande. Si les deux bits sont 1, le bit de résultat correspondant a la valeur 1. Sinon, le bit de résultat correspondant a la valeur 0.  
  
 Les deux opérandes de l’opérateur de bits AND doivent être de types intégraux. Les conversions arithmétiques courantes traitées dans [Conversions Standard](standard-conversions.md), sont appliquées aux opérandes.  
  
## <a name="operator-keyword-for-"></a>Mot clé operator pour &  
 Le `bitand` opérateur est l’équivalent textuel de ** & **. Il existe deux moyens d’accéder à la `bitand` opérateur dans vos programmes : incluez le fichier d’en-tête `iso646.h`, ou compilez avec le [/Za](../build/reference/za-ze-disable-language-extensions.md) option du compilateur (désactiver les extensions de langage).  
  
## <a name="example"></a>Exemple  
  
```  
// expre_Bitwise_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise AND  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0xFFFF;      // pattern 1111 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a & b ) << endl;   // prints "aaaa", pattern 1010 ...  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateurs intégrés, priorité et associativité C++](cpp-built-in-operators-precedence-and-associativity.md)  
 [Les opérateurs C++ intégrés, priorité et associativité](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs de bits C](../c-language/c-bitwise-operators.md)
