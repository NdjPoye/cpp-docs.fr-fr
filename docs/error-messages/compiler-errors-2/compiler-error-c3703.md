---
title: "Erreur du compilateur C3703 | Microsoft Docs"
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
  - "C3703"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3703"
ms.assetid: 7e3677d9-f2be-4c26-998f-423564e9023c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3703
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'gestionnaire d'événements' : une méthode de gestionnaire d'événements doit avoir la même classe de stockage que l''événement' source  
  
 Un [événement](../../cpp/event-handling.md) possède une classe de stockage différente de celle du gestionnaire d'événements auquel il est lié.  Cette erreur se produit, par exemple, si le gestionnaire d'événements est une fonction membre statique et si l'événement n'est pas statique.  Pour remédier à cette erreur, attribuez la même classe de stockage à l'événement et au gestionnaire d'événements.  
  
 L'exemple suivant génère l'erreur C3703 :  
  
```  
// C3703.cpp  
// C3703 expected  
#include <stdio.h>  
  
[event_source(type=native)]  
class CEventSrc {  
public:  
   __event static void MyEvent();  
};  
  
[event_receiver(type=native)]  
class CEventHandler {  
public:  
   // delete the following line to resolve  
   void MyHandler() {}  
  
   // try the following line instead  
   // static void MyHandler() {}  
  
   void HookIt(CEventSrc* pSource) {  
      __hook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);  
   }  
  
   void UnhookIt(CEventSrc* pSource) {  
      __unhook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);  
   }  
};  
  
int main() {  
   CEventSrc src;  
   CEventHandler hnd;  
  
   hnd.HookIt(&src);  
   __raise src.MyEvent();  
   hnd.UnhookIt(&src);  
}  
```