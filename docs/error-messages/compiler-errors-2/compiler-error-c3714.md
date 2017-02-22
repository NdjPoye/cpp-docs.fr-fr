---
title: "Erreur du compilateur C3714 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3714"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3714"
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C3714
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'méthode' : une méthode de gestionnaire d'événements doit avoir la même convention d'appel que la 'méthode' source  
  
 Vous avez défini une méthode de gestionnaire d'événements qui n'utilise pas la même convention d'appel que la méthode d'événement source.  Pour remédier à cette erreur, donnez à la méthode de gestionnaire d'événements les mêmes conventions d'appel qu'à la méthode d'événement source.  Dans le code ci\-dessous, par exemple, faites concorder les conventions d'appel de `handler1` et `event1` \([\_\_cdecl](../../cpp/cdecl.md) ou [\_\_stdcall](../../cpp/stdcall.md) ou autres\).  La suppression des mots clés de convention d'appel résoudra également le problème et aura pour effet que `event1` et `handler1` prendront par défaut la convention d'appel [thiscall](../../cpp/thiscall.md).  Pour plus d'informations, consultez [Conventions d'appel](../../cpp/calling-conventions.md).  
  
 L'exemple suivant génère l'erreur C3714 :  
  
```  
// C3714.cpp  
// compile with: /c  
// processor: x86  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void __cdecl event1();  
   // try the following line instead  
   // __event void __stdcall event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void __stdcall handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3714  
   }  
  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3714  
   }  
};  
```