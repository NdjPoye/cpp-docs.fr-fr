---
title: Erreur du compilateur C2498 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2498
dev_langs:
- C++
helpviewer_keywords:
- C2498
ms.assetid: 0839f12c-aaa4-4a02-bb33-7f072715dd14
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0324ebd2cb27e1d48221b72bec2caaea5c4fc698
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2498"></a>Erreur du compilateur C2498
'fonction' : 'novtable' peut uniquement être appliqué aux définitions ou déclarations de classe  
  
 Cette erreur peut être dû à l’aide de `__declspec(novtable)` avec une fonction.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2498 :  
  
```  
// C2498.cpp  
// compile with: /c  
void __declspec(novtable) f() {}   // C2498  
class __declspec(novtable) A {};   // OK  
```
