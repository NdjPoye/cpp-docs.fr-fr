---
title: Erreur du compilateur C3379 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3379
dev_langs:
- C++
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9fd5a8acf918a0f6b485cf9ba94ad759d58f7b2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3379"></a>Erreur du compilateur C3379
'classe' : une classe imbriquée ne peut pas avoir de spécificateur d’accès d’assembly dans le cadre de sa déclaration  
  
 Quand il est appliqué à un type managé, telles que la classe ou structure, le [public](../../cpp/public-cpp.md) et [privé](../../cpp/private-cpp.md) mots clés indiquent si la classe doit être exposée via les métadonnées de l’assembly. `public`ou `private` ne peut pas être appliqué à une classe imbriquée, qui héritera de l’accès à l’assembly de la classe englobante.  
  
 Lorsqu’il est utilisé avec [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), le `ref` et `value` mots clés indiquent qu’une classe est managée (consultez [les Classes et Structs](../../windows/classes-and-structs-cpp-component-extensions.md)).  
  
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
