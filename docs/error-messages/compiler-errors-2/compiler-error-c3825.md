---
title: "Erreur du compilateur C3825 | Microsoft Docs"
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
  - "C3825"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3825"
ms.assetid: 18e204a1-f26e-42c6-8d74-2b49cc95f940
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3825
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : une classe managée ou WinRT ne peut prendre en charge que des événements managés ou WinRT  
  
 Seuls les événements .NET sont pris en charge dans les classes managées.  Seuls les événements Windows Runtime sont pris en charge dans les classes Windows Runtime.  Pour corriger cette erreur dans du code managé, modifiez le paramètre de type de `event_source` et `event_receiver` de `native` à `managed`.  Vous pouvez également supprimer l'attribut.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3825 et montre comment la corriger :  
  
```  
// C3825a.cpp  
// compile with: /clr  
public delegate void del1();  
  
[event_source(native)]           // To fix, change 'native' to 'managed' or delete this line  
ref class CEventSrc  
{  
public:  
   event del1^ event1;       // C3825  
  
   void FireEvents() {  
      event1();  
   }  
};  
  
[event_receiver(native)]         // To fix, change 'native' to 'managed' or delete this line  
ref class CEventRec  
{  
public:  
   void handler1()  
   {  
      System::Console::WriteLine("Executing handler1().\n");  
   }  
   void HookEvents(CEventSrc^ pSrc)   
   {  
      pSrc->event1 += gcnew del1(this, &CEventRec::handler1);  
   }  
   void UnhookEvents(CEventSrc^ pSrc)   
   {  
      pSrc->event1 -= gcnew del1(this, &CEventRec::handler1);  
   }  
};  
  
int main()   
{  
   CEventSrc^ pEventSrc = gcnew CEventSrc;  
   CEventRec^ pEventRec = gcnew CEventRec;  
   pEventRec->HookEvents(pEventSrc);  
   pEventSrc->FireEvents();  
   pEventRec->UnhookEvents(pEventSrc);  
}  
```