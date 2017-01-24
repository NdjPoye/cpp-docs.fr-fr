---
title: "Erreur du compilateur C2843 | Microsoft Docs"
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
  - "C2843"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2843"
ms.assetid: 9d3f2ac4-eea5-4fed-abeb-e752f442bfcc
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2843
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : ne peut pas prendre l'adresse d'une donnée membre non static ni d'une méthode de type managé ou WinRT  
  
 Une instance est requise pour prendre l'adresse des membres de données non statiques d'une interface ou d'une classe managée ou WinRT.  
  
 L'exemple suivant génère l'erreur C2843 et montre comment la corriger :  
  
```  
// C2843_2.cpp  
// compile with: /clr  
public ref class C {  
public:  
   int m_i;  
};  
  
ref struct MyStruct {  
   static void sf() {}  
   void f() {}  
};  
  
int main() {  
   MyStruct ^ps = gcnew MyStruct;  
   void (__clrcall MyStruct::*F1)() = & MyStruct::f;   // C2843  
   void (__clrcall MyStruct::*F2)() = & ps->f;   // C2843  
   void (__clrcall MyStruct::*F3)();   // C2843  
  
   void (__clrcall *F5)() = MyStruct::sf;   // OK  
   void (__clrcall *F6)() = & ps->sf;   // OK  
  
   interior_ptr<int> i = &C::m_i; // C2843  
   C ^x = gcnew C();  
   interior_ptr<int> ii = &x->m_i;  
}  
```  
  
 L'exemple suivant génère l'erreur C2843 et montre comment la corriger :  
  
```  
// C2843.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
public __gc class C {  
public:  
   int m_i;  
};  
  
__gc struct MyStruct {  
   static void sf() {}  
   void f() {}  
};  
  
int main() {  
   MyStruct *ps = new MyStruct;  
   void (__clrcall MyStruct::*F1)() = & MyStruct::f;   // C2843  
   void (__clrcall MyStruct::*F2)() = & ps->f;   // C2843  
   void (__clrcall MyStruct::*F3)();   // C2843  
  
   void (__clrcall *F5)() = MyStruct::sf;   // OK  
   void (__clrcall *F6)() = & ps->sf;   // OK  
  
   int __gc *i = &C::m_i; // C2843  
   C *x = new C();  
   int __gc *i = &x->m_i;  
}  
```