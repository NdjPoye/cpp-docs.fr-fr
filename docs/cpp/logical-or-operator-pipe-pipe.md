---
title: 'Logique ou un opérateur : || | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '||'
dev_langs:
- C++
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd0642e9759eaa4d39eac680ba165af7dbbb0d44
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="logical-or-operator-"></a>Opérateur OR logique : ||
## <a name="syntax"></a>Syntaxe  
  
```  
  
logical-or-expression   
||  
 logical-and-expression  
  
```  
  
## <a name="remarks"></a>Notes  
 L’opérateur OR logique (`||`) retourne la valeur booléenne **true** si un ou les deux opérandes est **true** et retourne **false** dans le cas contraire. Les opérandes sont convertis implicitement vers le type `bool` avant leur évaluation, et le résultat est de type `bool`. L'opérateur OR logique présente une associativité de gauche à droite.  
  
 Les opérandes de l’opérateur OR logique ne sont pas nécessairement du même type, mais ils doivent être de type intégral ou pointeur. Les opérandes sont souvent des expressions relationnelles ou d'égalité.  
  
 Le premier opérande doit être complètement évalué et tous les effets secondaires terminés pour que l’évaluation de l’expression OR logique se poursuive.  
  
 Le second opérande est évalué seulement si le premier opérande équivaut à false (0). Cela permet d’éviter l’évaluation inutile du second opérande lorsque l’expression OR logique a pour valeur true.  
  
```  
printf( "%d" , (x == w || x == y || x == z) );  
```  
  
 Dans l'exemple ci-dessus, si `x` est égal à `w`, à `y` ou à `z`, le second argument de la fonction `printf` équivaut à true et la valeur 1 est affichée. Dans le cas contraire, il équivaut à false et la valeur 0 est affichée. Dès que l'une des conditions équivaut à true, l'évaluation cesse.  
  
## <a name="operator-keyword-for-124124"></a>Mot clé operator pour&#124;&#124;  
 Le **ou** opérateur est l’équivalent textuel de `||`. Il existe deux moyens d’accéder à la **ou** opérateur dans vos programmes : incluez le fichier d’en-tête `iso646.h`, ou compilez avec le [/Za](../build/reference/za-ze-disable-language-extensions.md) option du compilateur (désactiver les extensions de langage).  
  
## <a name="example"></a>Exemple  
  
```  
// expre_Logical_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical OR  
#include <iostream>  
using namespace std;  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b || b > c yields "  
         << (a < b || b > c) << endl  
         << "The false expression "  
         << "a > b || b > c yields "  
         << (a > b || b > c) << endl;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
[Les opérateurs C++ intégrés priorité et associativité](cpp-built-in-operators-precedence-and-associativity.md) [C++ intégrés opérateurs, priorité et associativité](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs logiques C](../c-language/c-logical-operators.md)