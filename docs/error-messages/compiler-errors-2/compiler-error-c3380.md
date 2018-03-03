---
title: Erreur du compilateur C3380 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3380
dev_langs:
- C++
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f8789889ab0d9ebe93941a438c286ed718ac4721
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3380"></a>Erreur du compilateur C3380
'class' : spécificateur d’accès à l’assembly non valide - seuls 'public' ou 'private' sont autorisés  
  
 En cas d’application à une classe managée ou à une structure, les mots clés [public](../../cpp/public-cpp.md) et [private](../../cpp/private-cpp.md) indiquent si la classe doit être exposée dans les métadonnées de l’assembly. Seuls `public` ou `private` peuvent être appliqués à une classe contenue dans un programme compilé avec [/clr](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Le `ref` et `value` lorsque utilisé avec les mots clés [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), indiquent qu’une classe est managée (consultez [les Classes et Structs](../../windows/classes-and-structs-cpp-component-extensions.md)).  
  
 L’exemple suivant génère l’erreur C3380 :  
  
```  
// C3380_2.cpp  
// compile with: /clr  
protected ref class A {   // C3380  
// try the following line instead  
// ref class A {  
public:  
   static int i = 9;  
};  
  
int main() {  
   A^ myA = gcnew A;  
   System::Console::WriteLine(myA->i);  
}  
```  
