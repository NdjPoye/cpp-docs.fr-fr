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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e8e5e441011c69e2b50b4565981d89a7730d542f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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