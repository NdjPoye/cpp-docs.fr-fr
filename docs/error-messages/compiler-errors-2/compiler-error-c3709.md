---
title: "Erreur du compilateur C3709 | Microsoft Docs"
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
  - "C3709"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3709"
ms.assetid: d5576b04-2f93-420a-8f3e-8b8e987e8dab
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3709
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : syntaxe incorrecte pour spécifier un événement dans \_\_hook\/\_\_unhook  
  
 Lorsque vous spécifiez une source d'événements avec [\_\_hook](../../cpp/hook.md) ou [\_\_unhook](../../cpp/unhook.md), le premier paramètre doit être une méthode d'événement valide et le second paramètre doit être un objet source d'événement valide \(pas une méthode\).  
  
 L'exemple suivant génère l'erreur C3709 :  
  
```  
// C3709.cpp  
// compile with: /LD  
[event_source(native)]  
class CEventSrc  
{  
public:  
   __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec  
{  
public:  
   void handler1()  
   {  
   }  
  
   void HookEvents(CEventSrc* pSrc)  
   {  
      __hook(bad, pSrc, CEventRec::handler1);   // C3709  
      // Try the following line instead:  
      // __hook(&CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
  
   void UnhookEvents(CEventSrc* pSrc)  
   {  
      __unhook(&CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
};  
```