---
title: "Opération de bits OR inclusif ou opérateur : || Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bitor
- '|'
dev_langs:
- C++
helpviewer_keywords:
- OR operator, bitwise inclusive
- bitwise operators, OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
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
ms.openlocfilehash: bb2fcc7c85e112b80929b2a8392f0e6c19ab97f2
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="bitwise-inclusive-or-operator-"></a>Opérateur de bits OR inclusif : |
## <a name="syntax"></a>Syntaxe  
  
```  
  
expression   
|  
 expression  
  
```  
  
## <a name="remarks"></a>Remarques  
 L’opérateur OR inclusif au niveau du bit (**&#124;**) compare chaque bit de son premier opérande au bit correspondant de son second opérande. Si l'un des bits est 1, le bit correspondant de résultat a la valeur 1. Sinon, le bit de résultat correspondant a la valeur 0.  
  
 Les deux opérandes de l’opérateur OR inclusif de bits doivent être de types intégraux. Les conversions arithmétiques courantes traitées dans [Conversions Standard](standard-conversions.md) sont appliquées aux opérandes.  
  
## <a name="operator-keyword-for-124"></a>Mot clé operator pour &#124;  
 Le `bitor` opérateur est l’équivalent textuel de **&#124;**. Il existe deux moyens d’accéder à la `bitor` opérateur dans vos programmes : incluez le fichier d’en-tête `iso646.h`, ou compilez avec le [/Za](../build/reference/za-ze-disable-language-extensions.md) option du compilateur (désactiver les extensions de langage).  
  
## <a name="example"></a>Exemple  
  
```  
// expre_Bitwise_Inclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise inclusive OR  
#include <iostream>  
using namespace std;  
  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Les opérateurs C++ intégrés, priorité et associativité](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs de bits C](../c-language/c-bitwise-operators.md)


