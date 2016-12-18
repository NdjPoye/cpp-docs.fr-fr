---
title: "Avertissement du compilateur (niveau 1) C4803 | Microsoft Docs"
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
  - "C4803"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4803"
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4803
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'méthode' : la méthode raise a une classe de stockage différente de celle de l'événement, 'événement'  
  
 Les méthodes d'événements doivent avoir la même classe de stockage que la déclaration event.  Le compilateur ajuste les méthodes d'événement de manière à ce que les classes de stockage soient les mêmes.  
  
 Cet avertissement peut se produire si une classe implémente un événement depuis une interface.  Le compilateur ne génère pas implicitement une méthode raise pour un événement dans une interface.  Lorsque vous implémentez cette interface dans une classe, le compilateur ne génère pas implicitement une méthode raise et cette méthode ne sera pas virtuelle, d'où l'avertissement.  
  
 Consultez le pragma [warning](../../preprocessor/warning.md) pour obtenir des informations sur la manière de désactiver un avertissement.  
  
## Exemple  
 L'erreur C4803 peut être générée à l'aide de **\/clr**.  Pour plus d'informations sur l'utilisation d'événements, consultez [event](../../windows/event-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C4803 :  
  
```  
// C4803.cpp  
// compile with: /clr /W1  
using namespace System;  
  
public delegate void Del();  
  
ref struct E {  
   Del ^ _pd1;  
   event Del ^ E1 {  
      void add (Del ^ pd1) {  
         _pd1 = dynamic_cast<Del ^>(Delegate::Combine(_pd1, pd1));  
      }  
  
      void remove(Del^ pd1) {  
         _pd1 = dynamic_cast<Del^> (Delegate::Remove(_pd1, pd1));  
      }  
  
      virtual void raise() {   // C4803 warning (remove virtual)  
         if (_pd1)  
            _pd1();  
      }  
   }  
  
   void func() {  
      Console::WriteLine("In E::func()");  
   }  
};  
  
int main() {  
   E ^ ep = gcnew E;  
   ep->E1 += gcnew Del(ep, &E::func);  
   ep->E1();  
   ep->E1 -= gcnew Del(ep, &E::func);  
   ep->E1();  
}  
```  
  
## Exemple  
 L'erreur C4803 peut être générée à l'aide de **\/clr:oldSyntax**.  L'exemple suivant génère l'erreur C4803 :  
  
```  
// C4803_b.cpp  
// compile with: /clr:oldSyntax /W1  
using namespace System;  
  
public __delegate void Del();  
  
__gc struct E {  
   Del* _pd1;  
   virtual __event void add_E1(Del* pd1) {  
      _pd1 = dynamic_cast<Del*> (Delegate::Combine(_pd1, pd1));  
   }  
  
   virtual __event void remove_E1(Del* pd1) {  
      _pd1 = dynamic_cast<Del*> (Delegate::Remove(_pd1, pd1));  
   }  
  
   __event void raise_E1 () {   // C4803, add virtual  
      if (_pd1)  
         _pd1->Invoke();  
   }  
  
   void func() {  
      Console::WriteLine("In E::func()");  
   }  
};  
  
int main() {  
   E* ep = new E;  
   ep->E1 += new Del(ep, &E::func);  
   ep->E1();  
   ep->E1 -= new Del(ep, &E::func);  
   ep->E1();  
}  
```