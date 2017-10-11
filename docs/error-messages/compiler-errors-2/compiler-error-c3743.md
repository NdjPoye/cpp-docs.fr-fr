---
title: Erreur du compilateur C3743 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3743
dev_langs:
- C++
helpviewer_keywords:
- C3743
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 71e35535a7e6c9916c6dd6ac563cfd5bdf76fbce
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3743"></a>Erreur du compilateur C3743
peut uniquement raccorder/décrocher la totalité d’une interface quand le paramètre 'layout_dependent' d’event_receiver a la valeur true  
  
 Le [__unhook](../../cpp/unhook.md) fonction varie selon le nombre de paramètres en fonction de la valeur passée à la `layout_dependent` paramètre dans le [event_receiver](../../windows/event-receiver.md) classe.  
  
 L’exemple suivant génère l’erreur C3743 :  
  
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
