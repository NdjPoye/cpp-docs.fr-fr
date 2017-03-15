---
title: "Erreur du compilateur C3706 | Microsoft Docs"
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
  - "C3706"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3706"
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3706
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : doit être une interface COM pour déclencher des événements COM  
  
 L'interface d'événement que vous utilisez pour déclencher des événements COM doit être une interface COM.  Dans cette situation, l'interface doit être définie à l'aide d'un attribut Visual C\+\+ ou être importée à l'aide de [\#import](../../preprocessor/hash-import-directive-cpp.md) à partir d'une bibliothèque de types possédant l'attribut embedded\_idl de \#import.  
  
 Notez que les lignes `#include` des fichiers d'en\-tête ATL illustrées dans l'exemple ci\-dessous sont nécessaires pour utiliser les événements COM.  Pour remédier à cette erreur, transformez `IEvents` \(l'interface d'événement\) en une interface COM en appliquant l'un des attributs suivants à la définition de l'interface : [object](../../windows/object-cpp.md), [dual](../../windows/dual.md) ou [dispinterface](../../windows/dispinterface.md).  
  
 Si une interface provient d'un fichier d'en\-tête généré par MIDL, le compilateur ne la reconnaît pas comme une interface COM.  
  
 L'exemple suivant génère l'erreur C3706 :  
  
```  
// C3706.cpp  
// compile with: /c  
// C3706 expected  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];  
  
// Uncomment the following line to resolve.  
// [object, uuid="12341234-1234-1234-1234-123412341237"]  
__interface IEvents : IUnknown {  
   HRESULT event1(/*[in]*/ int i);   // uncomment [in]  
};  
  
[dual, uuid="12341234-1234-1234-1234-123412341235"]  
__interface IBase {  
   HRESULT fireEvents();  
};  
  
[coclass, event_source(com), uuid="12341234-1234-1234-1234-123412341236"]  
class CEventSrc : public IBase {  
   public:  
   __event __interface IEvents;  
  
   HRESULT fireEvents() {  
      HRESULT hr = IEvents_event1(123);  
      return hr;  
   }  
};  
```