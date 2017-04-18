---
title: Erreur du compilateur C3485 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3485
dev_langs:
- C++
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 40c35bdb5be6fad108e612208b53773ceb4105e9
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3485"></a>Erreur du compilateur C3485
une définition d'expression lambda ne peut pas contenir de qualificateurs cv  
  
 Vous ne pouvez pas utiliser un qualificateur `const` ou `volatile` dans le cadre de la définition d’une expression lambda.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Supprimez le qualificateur `const` ou `volatile` de la définition de l’expression lambda.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3485, car il utilise le qualificateur `const` dans le cadre de la définition d’une expression lambda :  
  
```  
// C3485.cpp  
  
int main()  
{  
   auto x = []() const mutable {}; // C3485  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)
