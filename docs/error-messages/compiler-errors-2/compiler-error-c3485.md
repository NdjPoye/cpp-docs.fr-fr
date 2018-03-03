---
title: Erreur du compilateur C3485 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3485
dev_langs:
- C++
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7fb872161cc82878c7809e6ebcae901db0ba772f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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