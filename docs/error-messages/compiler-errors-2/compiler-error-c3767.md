---
title: "Erreur du compilateur C3767 | Microsoft Docs"
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
  - "C3767"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3767"
ms.assetid: 5247cdcd-639c-4527-bd37-37e74c4e8fab
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3767
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : la ou les fonctions candidates ne sont pas accessibles  
  
 Une fonction friend définie dans une classe n'est pas censée être traitée comme si elle était définie et déclarée dans la portée de l'espace de noms global.  Elle peut toutefois être trouvée par une recherche dépendant des arguments.  
  
 L'erreur C3767 peut également être due à une modification avec rupture : les types natifs sont désormais privés par défaut dans une compilation **\/clr**. Consultez [Visibilité du type](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) pour plus d'informations.  
  
 L'exemple suivant génère l'erreur C3767 :  
  
```  
// C3767a.cpp  
// compile with: /clr  
using namespace System;  
public delegate void TestDel();  
  
public ref class MyClass {  
public:  
   static event TestDel^ MyClass_Event;  
};  
  
public ref class MyClass2 : public MyClass {  
public:  
   void Test() {  
      MyClass^ patient = gcnew MyClass;  
      patient->MyClass_Event();  
    }  
};  
  
int main() {  
   MyClass^ x = gcnew MyClass;  
   x->MyClass_Event();   // C3767  
  
   // OK  
   MyClass2^ y = gcnew MyClass2();  
   y->Test();  
};  
```  
  
 L'exemple suivant génère l'erreur C3767 :  
  
```  
// C3767b.cpp  
// compile with: /clr:oldSyntax  
using namespace System;  
__delegate void TestDel();  
  
public __gc class MyClass {  
public:  
   static __event TestDel * MyClass_Event;  
};  
  
public __gc class MyClass2 : public MyClass {  
public:  
   void Test() {  
      MyClass* patient = new MyClass;  
      patient->MyClass_Event();  
    }  
};  
  
int main() {  
   MyClass* x = new MyClass;  
   x->MyClass_Event();   // C3767  
  
   // OK  
   MyClass2 * y = new MyClass2();  
   y->Test();  
};  
```  
  
 L'exemple suivant génère l'erreur C3767 :  
  
```  
// C3767c.cpp  
// compile with: /clr /c  
  
ref class Base  {  
protected:  
   void Method() {  
      System::Console::WriteLine("protected");  
   }  
};  
  
ref class Der : public Base {  
   void Method() {  
      ((Base^)this)->Method();   // C3767  
      // try the following line instead  
      // Base::Method();  
   }  
};  
```  
  
 L'exemple suivant génère l'erreur C3767 :  
  
```  
// C3767d.cpp  
// compile with: /clr:oldSyntax /c  
  
__gc class Base {  
protected:  
   void Method() {  
      System::Console::WriteLine("protected");  
   }  
};  
  
__gc class Der : public Base {  
   void Method() {  
      ((Base*)this)->Method();   // C3767  
      // try the following line instead  
      // Base::Method();  
   }  
};  
```  
  
 Dans Visual C\+\+ .NET 2002, le compilateur a modifié le mode de recherche des symboles.  Dans certains cas, il recherchait automatiquement des symboles dans un espace de noms spécifié.  Il utilise dorénavant une recherche qui dépend de l'argument.  
  
 L'exemple suivant génère l'erreur C3767 :  
  
```  
// C3767e.cpp  
namespace N {  
   class C {  
      friend void FriendFunc() {}  
      friend void AnotherFriendFunc(C* c) {}  
   };  
}  
  
int main() {  
   using namespace N;  
   FriendFunc();   // C3767 error  
   C* pC = new C();  
   AnotherFriendFunc(pC);   // found via argument-dependent lookup  
}  
```  
  
 Pour le code qui est valide dans Visual C\+\+ .NET 2003 et Visual C\+\+ .NET 2002, déclarez la fonction friend dans la portée de la classe et définissez\-la dans la portée de l'espace de noms :  
  
```  
// C3767f.cpp  
class MyClass {  
   int m_private;  
   friend void func();  
};  
  
void func() {  
   MyClass s;  
   s.m_private = 0;  
}  
  
int main() {  
   func();  
}  
```