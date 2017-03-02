---
title: Compilateur avertissement (niveau 1) C4803 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4803
dev_langs:
- C++
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 2581d4240306e88d75fe5fcc0249371005853b7e
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4803"></a>Avertissement du compilateur (niveau 1) C4803
'méthode' : la méthode raise a une classe de stockage différente de celle de l’événement, 'événement'  
  
Méthodes d’événements doivent avoir la même classe de stockage que la déclaration d’événement. Le compilateur ajuste les méthodes d’événement afin que les classes de stockage sont identiques.  
  
Cet avertissement peut se produire si vous avez une classe qui implémente un événement à partir d’une interface. Le compilateur ne génère pas implicitement une méthode raise pour un événement dans une interface. Lorsque vous implémentez cette interface dans une classe, le compilateur génère implicitement une méthode raise et cette méthode ne sera pas virtuelle, d'où l’avertissement. Pour plus d’informations sur les événements, consultez la page [événement](../../windows/event-cpp-component-extensions.md).  
  
Consultez la page [avertissement](../../preprocessor/warning.md) pragma pour plus d’informations sur la façon de désactiver un avertissement.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4803.  
  
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

