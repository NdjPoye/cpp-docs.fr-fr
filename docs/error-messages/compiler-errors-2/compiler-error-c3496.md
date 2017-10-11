---
title: Erreur du compilateur C3496 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3496
dev_langs:
- C++
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 86c80c4b708bd4315b2ce2ceaf7b61e0629a8b2e
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3496"></a>Erreur du compilateur C3496
'this' est toujours capturé par valeur : '&' ignoré  
  
 Vous ne pouvez pas capturer le pointeur `this` par référence.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Capturez le pointeur `this` par valeur.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3496, car une référence au pointeur `this` se trouve dans la liste de capture d’une expression lambda :  
  
```  
// C3496.cpp  
// compile with: /c  
  
class C  
{  
   void f()  
   {  
      [&this] {}(); // C3496  
   }  
};  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)
