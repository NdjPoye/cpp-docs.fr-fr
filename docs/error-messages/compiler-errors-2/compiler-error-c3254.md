---
title: Erreur du compilateur C3254 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3254
dev_langs:
- C++
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 104ee89c45d8a1134611535ab6aa9c62f09e139c
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3254"></a>Erreur du compilateur C3254
'substitution explicite' : classe contient une substitution explicite 'substitution', mais ne dérive pas d’une interface qui contient la déclaration de fonction  
  
 Lorsque vous [substituer explicitement](../../cpp/explicit-overrides-cpp.md) une méthode, la classe qui contient la substitution doit provenir directement ou indirectement, à partir du type qui contient la fonction que vous substituez.  
  
 L’exemple suivant génère l’erreur C3254 :  
  
```  
// C3254.cpp  
__interface I  
{  
   void f();  
};  
  
__interface I1 : I  
{  
};  
  
struct A /* : I1 */  
{  
   void I1::f()  
   {   // C3254, uncomment : I1 to resolve this C3254  
   }  
};  
  
int main()  
{  
}  
```
