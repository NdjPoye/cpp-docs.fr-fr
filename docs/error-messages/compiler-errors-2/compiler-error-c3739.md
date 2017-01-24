---
title: "Erreur du compilateur C3739 | Microsoft Docs"
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
  - "C3739"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3739"
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3739
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : syntaxe prise en charge uniquement quand le paramètre 'layout\_dependent' de event\_receiver a la valeur true  
  
 Vous avez essayé de raccorder une interface d'événements complète, mais `layout_dependent` sur l'attribut [event\_receiver](../../windows/event-receiver.md) n'est pas vrai ; vous devez raccorder un événement à la fois.  
  
 L'exemple suivant génère l'erreur C3739 :  
  
```  
// C3739.cpp  
struct A  
{  
   __event void e();  
};  
  
// event_receiver is implied  
// [ event_receiver(layout_dependent=false)]  
  
// use the following line instead  
// [event_receiver(com, layout_dependent=true), coclass ]  
struct B  
{  
   void f();  
   B(A* a)  
   {  
      __hook(A, a, &B::f);   // C3739  
      // use the following line instead to hook a single event  
      // __hook(&A::e, a, &B::f);  
   }  
};  
  
int main()  
{  
}  
```