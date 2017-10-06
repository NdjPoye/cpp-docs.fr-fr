---
title: "Opérateurs d’égalité : == et ! = | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- not_eq
- '!='
- ==
dev_langs:
- C++
helpviewer_keywords:
- '!= operator'
- equality operator
- not equal to comparison operator
- equality operator [C++], syntax
- == operator
- not_eq operator
- equal to operator
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
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
ms.openlocfilehash: 5412869204f088e321d2a41da407026f9447eb82
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="equality-operators--and-"></a>Opérateurs d'égalité : == et !=
## <a name="syntax"></a>Syntaxe  
  
```  
expression == expression  
expression != expression  
```  
  
## <a name="remarks"></a>Remarques  
 Les opérateurs d’égalité binaires comparent l’égalité ou l’inégalité stricte de leurs opérandes.  
  
 Les opérateurs d'égalité, égal à (`==`) et différent de (`!=`), ont une priorité inférieure aux opérateurs relationnels, mais ils se comportent de la même manière. Le type de résultat pour ces opérateurs est `bool`.  
  
 L’opérateur égal à (`==`) renvoie **true** (1) si les deux opérandes ont la même valeur ; sinon, elle retourne **false** (0). L’opérateur non-égal à (`!=`) renvoie **true** si les opérandes n’ont pas la même valeur ; sinon, elle retourne **false**.  
  
## <a name="operator-keyword-for-"></a>Mot clé d'opérateur pour !=  
 L'opérateur `not_eq` est l'équivalent textuel de `!=`. Il existe deux moyens d’accéder à la `not_eq` opérateur dans vos programmes : incluez le fichier d’en-tête `iso646.h`, ou compilez avec le [/Za](../build/reference/za-ze-disable-language-extensions.md) option du compilateur (désactiver les extensions de langage).  
  
## <a name="example"></a>Exemple  
  
```  
// expre_Equality_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   cout  << boolalpha  
         << "The true expression 3 != 2 yields: "  
         << (3 != 2) << endl  
         << "The false expression 20 == 10 yields: "  
         << (20 == 10) << endl;  
}  
```  
  
 Les opérateurs d'égalité permettent de comparer les pointeurs à des membres du même type. Dans ce type de comparaison, les conversions de pointeur vers membre sont effectuées. Les conversions de pointeur vers membre peuvent également être comparées à une expression constante qui a pour valeur 0.  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions avec opérateurs binaires](../cpp/expressions-with-binary-operators.md)   
 [Les opérateurs C++ intégrés, priorité et associativité](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs relationnels et d’égalité C](../c-language/c-relational-and-equality-operators.md)
