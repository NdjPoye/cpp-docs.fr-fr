---
title: Erreur du compilateur C3865 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3865
dev_langs:
- C++
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: af0873d70fcb4f947e838afba130279edf705ced
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3865"></a>Erreur du compilateur C3865
'convention_appel' : peut uniquement être utilisé sur des fonctions membres natives  
  
 Une convention d’appel a été utilisé sur une fonction qui a été soit une fonction globale ou une fonction membre managée. La convention d’appel peut être utilisé uniquement sur une fonction membre (non managée) native.  
  
 Pour plus d’informations, consultez [Conventions d’appel](../../cpp/calling-conventions.md).  
  
 L’exemple suivant génère l’erreur C3865 :  
  
```  
// C3865.cpp  
// compile with: /clr  
// processor: x86  
void __thiscall Func(){}   // C3865  
  
// OK  
struct MyType {  
   void __thiscall Func(){}  
};  
```
