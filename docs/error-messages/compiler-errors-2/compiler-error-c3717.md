---
title: "Erreur du compilateur C3717 | Microsoft Docs"
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
  - "C3717"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3717"
ms.assetid: ae4fceb1-2583-4577-b2f1-40971a017055
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3717
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'méthode' : une méthode qui déclenche des événements ne peut pas être définie  
  
 Vous avez déclaré une méthode d'événement qui inclut une implémentation.  Une déclaration de méthode [\_\_event](../../cpp/event.md) ne peut pas avoir de définition.  Pour remédier à cette erreur, assurez\-vous qu'aucune déclaration de méthode d'événement ne comporte de définition.  Dans le code ci\-dessous, par exemple, supprimez le corps de fonction de la déclaration `event1` comme indiqué par les commentaires.  
  
 L'exemple suivant génère l'erreur C3717 :  
  
```  
// C3717.cpp  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void event1() {   // C3717  
   }  
  
   // remove definition for event1 and substitute following declaration  
   // __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void handler1() {  
   }  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
};  
  
int main() {  
}  
```