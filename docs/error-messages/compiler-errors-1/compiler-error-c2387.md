---
title: "Erreur du compilateur C2387 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2387"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2387"
ms.assetid: 6847b8e1-ffac-458d-ab88-0c92f72f2527
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2387
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : classe de base ambiguë  
  
 Le compilateur n'a pas pu résoudre clairement un appel de fonction, car la fonction existe dans plusieurs classes de base.  
  
 Pour remédier à cette erreur, supprimez une des classes de base de l'héritage, ou qualifiez explicitement l'appel de fonction.  
  
 L'exemple suivant génère l'erreur C2387 :  
  
```  
// C2387.cpp  
namespace N1 {  
   struct B {  
      virtual void f() {  
      }  
   };  
}  
  
namespace N2 {  
   struct B {  
      virtual void f() {  
      }  
   };  
}  
  
struct D : N1::B, N2::B {  
   virtual void f() {  
      B::f();   // C2387  
      // try the following line instead  
      // N1::B::f();  
   }  
};  
  
int main() {  
   D aD;  
   aD.f();  
}  
```