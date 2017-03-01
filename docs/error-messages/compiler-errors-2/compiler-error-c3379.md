---
title: Erreur du compilateur C3379 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3379
dev_langs:
- C++
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
caps.latest.revision: 10
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
ms.openlocfilehash: 16c62e48a0190096e04dc4ccf0c17ca66c2f4094
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3379"></a>Erreur du compilateur C3379
'classe' : une classe imbriquée ne peut pas avoir de spécificateur d’accès d’un assembly dans le cadre de sa déclaration  
  
 Lorsqu’il est appliqué à un type managé, telles que la classe ou structure, le [public](../../cpp/public-cpp.md) et [privé](../../cpp/private-cpp.md) mots clés indiquent si la classe doit être exposée via les métadonnées de l’assembly. `public`ou `private` ne peut pas être appliqué à une classe imbriquée, qui héritera de l’accès à l’assembly de la classe englobante.  
  
 Lorsqu’il est utilisé avec [/clr](../../build/reference/clr-common-language-runtime-compilation.md), le `ref` et `value` mots clés indiquent qu’une classe est managée (voir [les Classes et Structs](../../windows/classes-and-structs-cpp-component-extensions.md)).  
  
 L’exemple suivant génère l’erreur C3379 :  
  
```  
// C3379a.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class A {  
public:  
   static int i = 9;  
  
   public ref class BA {   // C3379  
   // try the following line instead  
   // ref class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A^ myA = gcnew A;  
   Console::WriteLine(myA->i);  
  
   A::BA^ myBA = gcnew A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```  

