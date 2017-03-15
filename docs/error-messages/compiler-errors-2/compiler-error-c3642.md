---
title: "Erreur du compilateur C3642 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3642"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3642"
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Erreur du compilateur C3642
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type\_retour\/args' : impossible d'appeler une fonction avec la convention d'appel \_\_clrcall à partir du code natif  
  
 Une fonction marquée avec la convention d'appel [\_\_clrcall](../../cpp/clrcall.md) ne peut pas être appelée à partir du code natif \(non managé\).  
  
 *return\_type\/args* est le nom de la fonction ou le type de la fonction `__clrcall` que vous essayez d'appeler.  Un type est utilisé lorsque vous appelez via un pointeur fonction.  
  
 Pour appeler une fonction managée à partir d'un contexte natif, vous pouvez ajouter une fonction "wrapper" qui appelle la fonction `__clrcall`.  Vous pouvez également utiliser le mécanisme de marshaling CLR ; pour plus d'informations, consultez [Comment : marshaler des pointeurs fonction à l'aide de PInvoke](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md).  
  
 L'exemple suivant génère l'erreur C3642 :  
  
```  
// C3642.cpp  
// compile with: /clr  
using namespace System;  
struct S {  
   void Test(String ^ s) {   // CLR type in signature, implicitly __clrcall  
      Console::WriteLine(s);  
   }  
   void Test2(char * s) {  
      Test(gcnew String(s));  
   }  
};  
  
#pragma unmanaged  
int main() {  
   S s;  
   s.Test("abc");   // C3642  
   s.Test2("abc");   // OK  
}  
```