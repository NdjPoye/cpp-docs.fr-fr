---
title: "Erreur du compilateur C3379 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3379"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3379"
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3379
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : une classe imbriquée ne peut pas avoir de spécificateur d'accès à l'assembly comme partie de sa déclaration  
  
 En cas d'application à une classe managée ou à un struct, les mots clés [public](../../cpp/public-cpp.md) et [private](../../cpp/private-cpp.md) indiquent si la classe doit être exposée via les métadonnées de l'assembly.  `public` ou `private` ne peut pas être appliqué à une classe imbriquée, qui héritera de l'accès à l'assembly de la classe englobante.  
  
 Lorsqu'ils sont utilisés avec [\/clr](../../build/reference/clr-common-language-runtime-compilation.md), les mots clés `ref` et `value` indiquent qu'une classe est managée \(voir [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)\).  
  
 L'exemple suivant génère l'erreur C3379 :  
  
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
  
 L'exemple suivant génère l'erreur C3379 :  
  
```  
// C3379b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
public __gc class A {  
public:  
   static int i = 9;  
  
   public __gc class BA {   // C3379  
   // try the following line instead  
   // __gc class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A *myA = new A;  
   Console::WriteLine(myA->i);  
  
   A::BA *myBA = new A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```