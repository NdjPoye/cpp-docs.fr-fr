---
title: "Erreur du compilateur C2039 | Microsoft Docs"
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
  - "C2039"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2039"
ms.assetid: f9dfd521-9b36-4454-a69c-d63f45b606bb
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2039
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur1' : n'est pas membre de 'identificateur2'  
  
 Le code appelle de manière incorrecte ou fait référence à un membre d'une structure, d'une classe ou d'une union.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2039 :  
  
```  
// C2039.cpp  
struct S {  
   int mem0;  
} s, *pS = &s;  
  
int main() {  
   pS->mem1 = 0;   // C2039 mem1 is not a member  
   pS->mem0 = 0;   // OK  
}  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C2039 :  
  
```  
// C2039_b.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Console::WriteLine( "{0}", DateTime::get_Now());   // C2039  
   Console::WriteLine( "{0}", DateTime::Now);   // OK  
   Console::WriteLine( "{0}", DateTime::Now::get());   // OK  
}  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C2039 :  
  
```  
// C2039_c.cpp  
// compile with: /clr /c  
ref struct S {  
   property int Count {  
     int get();  
     void set(int i){}  
   };  
};  
  
int S::get_Count() { return 0; }   // C2039  
int S::Count::get() { return 0; }   // OK  
```  
  
## Exemple  
 L'erreur C2039 peut également se produire si vous essayez d'accéder de manière incorrecte à un indexeur par défaut.  L'exemple suivant définit un composant créé en C\#.  
  
```  
// C2039_d.cs  
// compile with: /target:library  
// a C# program  
[System.Reflection.DefaultMember("Item")]  
public class B {  
   public int Item {  
      get { return 13; }  
      set {}  
   }  
};  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C2039 :  
  
```  
// C2039_e.cpp  
// compile with: /clr  
using namespace System;  
#using "c2039_d.dll"  
  
int main() {  
   B ^ b = gcnew B;  
   int n = b->default;   // C2039  
   // try the following line instead  
   // int n = b->Item;  
   Console::WriteLine(n);  
}  
```  
  
## Exemple  
 L'erreur C2039 peut également se produire si vous utilisez des génériques.  L'exemple suivant génère l'erreur C2039 :  
  
```  
// C2039_f.cpp  
// compile with: /clr  
interface class I {};  
  
ref struct R : public I {  
   virtual void f3() {}  
};  
  
generic <typename T>  
where T : I  
void f(T t) {  
   t->f3();   // C2039  
   safe_cast<R^>(t)->f3();   // OK  
}  
  
int main() {  
   f(gcnew R());  
}  
```  
  
## Exemple  
 C2039 peut se produire lorsque vous essayez de diffuser des ressources managées ou non managées.  Pour plus d'informations, consultez [Destructeurs et finaliseurs](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
 L'exemple suivant génère l'erreur C2039 :  
  
```  
// C2039_g.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Threading;  
  
void CheckStatus( Object^ stateInfo ) {}  
  
int main() {  
   ManualResetEvent^ event = gcnew ManualResetEvent( false );     
   TimerCallback^ timerDelegate = gcnew TimerCallback( &CheckStatus );  
   Timer^ stateTimer = gcnew Timer( timerDelegate, event, 1000, 250 );  
  
   ((IDisposable ^)stateTimer)->Dispose();   // C2039  
  
   stateTimer->~Timer();   // OK  
}  
```