---
title: Erreur du compilateur C3701 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3701
dev_langs:
- C++
helpviewer_keywords:
- C3701
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 723deeb35dc16aff4535c1961261ba705f8ee364
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3701"></a>Erreur du compilateur C3701
'fonction' : event_source n’a pas d’événements  
  
 Vous avez tenté d’utiliser [event_source](../../windows/event-source.md) sur une classe qui n’a aucune méthode d’événement. Pour corriger cette erreur, ajoutez un ou plusieurs événements à la classe.  
  
 L’exemple suivant génère l’erreur C3701 :  
  
```  
// C3701.cpp  
[ event_source(native) ]  
class CEventSrc {  
public:  
   // uncomment the following line to resolve this C3701  
   // __event void fireEvent(int i);  
};   // C3701  
  
int main() {  
}  
```
