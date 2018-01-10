---
title: Erreur du compilateur C3495 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3495
dev_langs: C++
helpviewer_keywords: C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3818f42410fd97d5df9b157828658c30ac9974e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3495"></a>Erreur du compilateur C3495
'var' : une capture lambda doit avoir une durée de stockage automatique  
  
 Vous ne pouvez pas capturer une variable qui n’a pas de durée de stockage automatique, telle qu’une variable qui est marquée `static` ou `extern`.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Ne passez pas une variable `static` ni `extern` à la liste de capture de l’expression lambda.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3495, car la variable `static` `n` figure dans la liste de capture d’une expression lambda :  
  
```  
// C3495.cpp  
  
int main()  
{  
   static int n = 66;  
   [&n]() { return n; }(); // C3495  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)   


