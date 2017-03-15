---
title: "Erreur du compilateur C2108 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2108"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2108"
ms.assetid: c84f0b47-5e2c-47d2-8edb-427a40e17c36
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2108
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'indice n'est pas de type intégral  
  
 L'indice de tableau est une expression non entière.  
  
## Exemple  
 L'erreur C2108 peut se produire si vous utilisez incorrectement le pointeur `this` d'un type valeur pour accéder à l'indexeur par défaut de ce type.  Pour plus d'informations, consultez [Sémantique de ce pointeur](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).  
  
 L'exemple suivant génère l'erreur C2108.  
  
```  
// C2108.cpp  
// compile with: /clr  
using namespace System;  
  
value struct B {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
   void Test() {  
      Console::WriteLine("{0}", this[3.3]);   // C2108  
      Console::WriteLine("{0}", this->default[3.3]);   // OK  
   }  
};  
  
int main() {  
   B ^ myb = gcnew B();  
   myb->Test();  
}  
```