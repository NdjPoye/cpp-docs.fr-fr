---
title: 'Un&#39;opérateur de complément s : ~ | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- "~"
dev_langs:
- C++
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a10c8f3df2a1f2f27ee33450a52132e8184d4232
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="one39s-complement-operator-"></a>Un&#39;opérateur de complément s : ~
## <a name="syntax"></a>Syntaxe  
  
```  
  
~ cast-expression  
```  
  
## <a name="remarks"></a>Notes  
 L'opérateur de complément à un (`~`), parfois appelé l'opérateur de complément de bits, génère un complément à un au niveau du bit de son opérande. Autrement dit, chaque bit qui est 1 dans l'opérande est 0 dans le résultat. Inversement, chaque bit qui est 0 dans l’opérande est 1 dans le résultat. L'opérande de l'opérateur de complément à un doit être un type intégral.  
  
## <a name="operator-keyword-for-"></a>Mot clé Operator pour ~  
 L'opérateur `compl` est l'équivalent textuel de `~`. Il existe deux moyens d’accéder à la `compl` opérateur dans vos programmes : incluez le fichier d’en-tête `iso646.h`, ou compilez avec [/Za](../build/reference/za-ze-disable-language-extensions.md).  
  
## <a name="example"></a>Exemple  
  
```  
// expre_One_Complement_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main () {  
   unsigned short y = 0xFFFF;  
   cout << hex << y << endl;  
   y = ~y;   // Take one's complement  
   cout << hex << y << endl;  
}  
```  
  
 Dans cet exemple, la nouvelle valeur assignée à `y` est le complément à 1 de la valeur non signée 0xFFFF ou 0x0000.  
  
 La promotion intégrale est exécutée sur les opérandes intégraux et le type résultant est le type vers lequel l’opérande est promu. Consultez [Conversions Standard](standard-conversions.md) pour plus d’informations sur la façon dont la promotion est effectuée.  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Les opérateurs C++ intégrés, priorité et associativité](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs arithmétiques unaires](../c-language/unary-arithmetic-operators.md)