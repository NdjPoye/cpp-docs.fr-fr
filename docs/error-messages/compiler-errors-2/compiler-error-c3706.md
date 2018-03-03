---
title: Erreur du compilateur C3706 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3706
dev_langs:
- C++
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2b33ea3c7de9afc605622cc55f4a45f73350d7db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3706"></a>Erreur du compilateur C3706
'fonction' : doit être une interface COM pour déclencher des événements COM  
  
 L’interface d’événement que vous utilisez pour déclencher des événements COM doit être une interface COM. Dans ce cas, l’interface doit être définie à l’aide d’un attribut Visual C++ ou importées à l’aide [#import](../../preprocessor/hash-import-directive-cpp.md) à partir d’une bibliothèque de types possédant l’attribut embedded_idl de #import.  
  
 Notez que le `#include` lignes des fichiers d’en-tête ATL illustrées dans l’exemple ci-dessous sont requises pour l’utilisation des événements COM. Pour corriger cette erreur, rendez `IEvents` (l’interface d’événement) une interface COM en appliquant une de ces attributs à la définition d’interface : [objet](../../windows/object-cpp.md), [double](../../windows/dual.md), ou [ dispinterface](../../windows/dispinterface.md).  
  
 Si une interface provient d’un fichier d’en-tête généré par MIDL, le compilateur ne la reconnaît pas comme une interface COM.  
  
 L’exemple suivant génère l’erreur C3706 :  
  
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