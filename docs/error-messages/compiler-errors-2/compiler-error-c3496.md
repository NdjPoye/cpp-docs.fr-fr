---
title: Erreur du compilateur C3496 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
ms.openlocfilehash: 72013d9345361bfbf0ee1dedecb27402850520c8
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3496"></a>Erreur du compilateur C3496
'this' est toujours capturé par valeur : '&' ignoré  
  
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
