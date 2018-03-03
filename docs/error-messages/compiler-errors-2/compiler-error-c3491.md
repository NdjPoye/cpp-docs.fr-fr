---
title: Erreur du compilateur C3491 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3491
dev_langs:
- C++
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c8c126ae0533424c19fd29ea48dbea8c3d7e8971
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3491"></a>Erreur du compilateur C3491
'variable' : impossible de modifier une capture par valeur dans une expression lambda non mutable  
  
 Une expression lambda non mutable ne peut pas modifier la valeur d’une variable capturée par valeur.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Déclarez votre expression lambda avec le mot clé `mutable` , ou  
  
-   Passez la variable par référence à la liste de capture de l’expression lambda.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3491, car le corps d’une expression lambda non mutable modifie la variable de capture `m`:  
  
```  
// C3491a.cpp  
  
int main()  
{  
   int m = 55;  
   [m](int n) { m = n; }(99); // C3491  
}  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant résout l’erreur C3491 en déclarant l’expression lambda avec le mot clé `mutable` :  
  
```  
// C3491b.cpp  
  
int main()  
{  
   int m = 55;  
   [m](int n) mutable { m = n; }(99);  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)