---
title: "Erreur du compilateur C3743 | Microsoft Docs"
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
  - "C3743"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3743"
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3743
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

peut uniquement raccorder\/décrocher la totalité d'une interface quand le paramètre 'layout\_dependent' de event\_receiver a la valeur true  
  
 Le nombre de paramètres de la fonction [\_\_unhook](../../cpp/unhook.md) varie en fonction de la valeur passée au paramètre `layout_dependent` dans la classe [event\_receiver](../../windows/event-receiver.md).  
  
 L'exemple suivant génère l'erreur C3743 :  
  
```  
// C3743.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
[module(name="xx")];  
[object] __interface I { HRESULT f(); };  
  
[event_receiver(com, layout_dependent=true), coclass]  
struct R : I {  
        HRESULT f() {  
      return 0;  
   }  
        R() {  
   }  
  
   R(I* a) {  
      __hook(I, a, &R::f);   // C3743  
      // The following line resolves the error.  
      // __hook(I, a);  
   }  
};  
```