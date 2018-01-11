---
title: Erreur du compilateur C3865 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3865
dev_langs: C++
helpviewer_keywords: C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cec5eabe6f4fa62648e9d3787d8ef2d2133f7736
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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