---
title: Erreur du compilateur C3182 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3182
dev_langs:
- C++
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 3dfd76788c55e74625172dedf2ceb5b8bdfaa061
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3182"></a>Erreur du compilateur C3182
'classe' : une déclaration d’accès ou déclaration using de membre n’est pas conforme dans géré ou WinRTtype  
  
 A [à l’aide de](../../cpp/using-declaration.md) déclaration n’est pas valide dans tous les formulaires de classes managées.  
  
 L'exemple suivant génère l'erreur C3182 et montre comment la corriger.  
  
```  
// C3182a.cpp  
// compile with: /clr /c  
ref struct B {  
   void mf(int) {  
   }  
};  
  
ref struct D : B {  
   using B::mf;   // C3182, delete to resolve  
   void mf(char) {  
   }  
};  
```  
