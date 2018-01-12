---
title: Erreur du compilateur C3714 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3714
dev_langs: C++
helpviewer_keywords: C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 69f3f5c90524b02cad8a36babaceeb32544e7aff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3714"></a>Erreur du compilateur C3714
'méthode' : une méthode de gestionnaire d’événements doit avoir la même convention d’appel en tant que la source 'méthode'  
  
 Vous avez défini une méthode de gestionnaire d’événements qui n’utilise pas la même convention d’appel en tant que la méthode d’événement source. Pour corriger cette erreur, donnez à la méthode de gestionnaire d’événements les mêmes conventions d’appel que ceux de la méthode d’événement source. Par exemple, dans le code ci-dessous, vérifiez les conventions d’appel de `handler1` et `event1` correspond à ([__cdecl](../../cpp/cdecl.md) ou [__stdcall](../../cpp/stdcall.md) ou d’autres). Suppression d’appel de mots clés de convention les deux déclarations d’également résoudre le problème et provoquer `event1` et `handler1` à la valeur par défaut pour le [thiscall](../../cpp/thiscall.md) convention d’appel. Consultez [Conventions d’appel](../../cpp/calling-conventions.md) pour plus d’informations.  
  
 L’exemple suivant génère l’erreur C3714 :  
  
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