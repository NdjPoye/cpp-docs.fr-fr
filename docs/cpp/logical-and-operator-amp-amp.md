---
title: 'Opérateur AND logique : &amp; &amp; | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '&&'
dev_langs:
- C++
helpviewer_keywords:
- logical AND operator
- AND operator
- '&& operator'
ms.assetid: 50cfa664-a8c4-4b31-9bab-2f80d7cd2d1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f683b7ff17a1dd3945f5cb554a7440ab47fad454
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="logical-and-operator-ampamp"></a>Opérateur AND logique : &amp;&amp;
## <a name="syntax"></a>Syntaxe  
  
```  
  
expression   
&&  
 expression  
  
```  
  
## <a name="remarks"></a>Notes  
 L’opérateur AND logique (**&&**) retourne la valeur booléenne **true** si les deux opérandes sont **true** et retourne **false** dans le cas contraire. Les opérandes sont convertis implicitement vers le type `bool` avant leur évaluation, et le résultat est de type `bool`. L'opérateur logique présente une associativité de gauche à droite.  
  
 Les opérandes de l’opérateur logique AND n’ont pas besoin d’être du même type, mais ils doivent être de type intégral ou de type pointeur. Les opérandes sont souvent des expressions relationnelles ou d’égalité.  
  
 Le premier opérande est complètement évalué et tous les effets secondaires sont terminés avant de continuer l’évaluation de l’expression AND logique.  
  
 Le deuxième opérande est évalué uniquement si le premier opérande a la valeur true (une valeur différente de zéro). Cette évaluation élimine l’évaluation inutile du deuxième opérande lorsque l’expression AND logique est false. Vous pouvez utiliser cette évaluation de court-circuit pour empêcher le déréférencement du pointeur NULL, comme indiqué dans l'exemple suivant :  
  
```  
char *pch = 0;  
...  
(pch) && (*pch = 'a');  
```  
  
 Si `pch` est null (0), le côté droit de l'expression n'est jamais évalué. Par conséquent, l'assignation via un pointeur null est impossible.  
  
## <a name="operator-keyword-for-"></a>Mot clé Operator pour &&  
 Le **et** opérateur est l’équivalent textuel de **&&**. Il existe deux moyens d’accéder à la **et** opérateur dans vos programmes : incluez le fichier d’en-tête `iso646.h`, ou compilez avec le [/Za](../build/reference/za-ze-disable-language-extensions.md) option du compilateur (désactiver les extensions de langage).  
  
## <a name="example"></a>Exemple  
  
```  
// expre_Logical_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical AND  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b && b < c yields "  
         << (a < b && b < c) << endl  
         << "The false expression "  
         << "a > b && b < c yields "  
         << (a > b && b < c) << endl;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Les opérateurs C++ intégrés priorité et associativité](cpp-built-in-operators-precedence-and-associativity.md) [C++ intégrés opérateurs, priorité et associativité](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs logiques C](../c-language/c-logical-operators.md)