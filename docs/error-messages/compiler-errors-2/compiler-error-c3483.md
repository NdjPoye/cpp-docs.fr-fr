---
title: Erreur du compilateur C3483 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- C3483
dev_langs:
- C++
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e2ea5c703e9617bd419a3e390f143c0defd7ca9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3483"></a>Erreur du compilateur C3483
'var' figure déjà dans la liste de capture lambda  
  
 Vous avez passé plusieurs fois la même variable à la liste de capture d’une expression lambda.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Supprimez toutes les instances supplémentaires de la variable de la liste de capture.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3483, car la variable `n` apparaît plusieurs fois dans la liste de capture de l’expression lambda :  
  
```  
// C3483.cpp  
  
int main()  
{  
   int m = 6, n = 5;  
   [m,n,n] { return n + m; }(); // C3483  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)