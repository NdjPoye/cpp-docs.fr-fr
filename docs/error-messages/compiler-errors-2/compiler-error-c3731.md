---
title: "Erreur du compilateur C3731 | Microsoft Docs"
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
  - "C3731"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3731"
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3731
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

événement 'fonction1' et gestionnaire 'fonction2' incompatibles ; la source d'événements et le gestionnaire d'événements doivent avoir le même type d'événement  
  
 La source d'événements et le récepteur d'événements doivent être du même type \(par exemple, les types `native` vs. `com` \).  Pour remédier à cette erreur, faites concorder les types de la source d'événements et du gestionnaire d'événements.  
  
 L'exemple suivant génère l'erreur C3731 :  
  
```  
// C3731.cpp  
// compile with: /clr  
#using <mscorlib.dll>  
[event_source(native)]  
struct A {  
   __event void MyEvent();  
};  
  
[event_receiver(managed)]  
// try the following line instead  
// [event_receiver(native)]  
struct B {  
   void func();  
   B(A a) {  
      __hook(&A::MyEvent, &a, &B::func);   // C3731  
   }  
};  
  
int main() {  
}  
```