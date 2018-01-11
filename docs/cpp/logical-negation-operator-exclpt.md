---
title: "Opérateur de négation logique : ! | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '!'
- Not
dev_langs: C++
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f63d36fc5974241fb624dd3a2afc863142516e9b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="logical-negation-operator-"></a>Opérateur de négation logique : !
## <a name="syntax"></a>Syntaxe  
  
```  
  
! cast-expression  
```  
  
## <a name="remarks"></a>Notes  
 L’opérateur de négation logique (**!**) inverse la signification de son opérande. L’opérande doit être de type arithmétique ou pointeur (ou une expression qui a pour valeur le type arithmétique ou pointeur). L'opérande est implicitement converti en type `bool`. Le résultat est **true** si l’opérande converti est **false**; le résultat est **false** si l’opérande converti est **true**. Le résultat est de type `bool`.  
  
 Pour une expression *e*, l’expression unaire **!** *e* est équivalent à l’expression **(***e* `==` 0), sauf si les opérateurs surchargés sont impliqués.  
  
## <a name="operator-keyword-for-"></a>Mot clé Operator pour !  
 Le **pas** opérateur est l’équivalent textuel de **!**. Il existe deux moyens d’accéder à la **pas** opérateur dans vos programmes : incluez le fichier d’en-tête `iso646.h`, ou compilez avec le [/Za](../build/reference/za-ze-disable-language-extensions.md) option du compilateur (désactiver les extensions de langage).  
  
## <a name="example"></a>Exemple  
  
```  
// expre_Logical_NOT_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 0;  
   if (!i)  
      cout << "i is zero" << endl;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Les opérateurs C++ intégrés, priorité et associativité](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs arithmétiques unaires](../c-language/unary-arithmetic-operators.md)