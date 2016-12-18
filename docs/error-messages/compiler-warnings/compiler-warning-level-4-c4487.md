---
title: "Avertissement du compilateur (niveau 4) C4487 | Microsoft Docs"
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
  - "C4487"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4487"
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4487
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction\_classe\_dérivée' : correspond à la méthode non virtuelle héritée 'fonction\_classe\_base' mais n'est pas explicitement marqué comme 'new'  
  
 Une fonction contenue dans une classe dérivée a la même signature qu'une fonction de classe de base non virtuelle.  L'erreur C4487 vous rappelle que la fonction de classe dérivée ne substitue pas la fonction de classe de base.  Marquez explicitement la fonction de classe dérivée comme `new` pour résoudre cet avertissement.  
  
 Pour plus d'informations, consultez [new \(new slot in vtable\)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4487 :  
  
```  
// C4487.cpp  
// compile with: /W4 /clr  
using namespace System;  
public ref struct B {  
   void f() { Console::WriteLine("in B::f"); }  
   void g() { Console::WriteLine("in B::g"); }  
};  
  
public ref struct D : B {  
   void f() { Console::WriteLine("in D::f"); }   // C4487  
   void g() new { Console::WriteLine("in D::g"); }   // OK  
};  
  
int main() {  
   B ^ a = gcnew D;  
   // will call base class functions  
   a->f();  
   a->g();  
}  
```