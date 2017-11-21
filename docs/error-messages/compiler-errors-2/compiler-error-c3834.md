---
title: Erreur du compilateur C3834 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3834
dev_langs: C++
helpviewer_keywords: C3834
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8a827b2abe6352f083dbd21bdd9647af9b3b1f5c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3834"></a>Erreur du compilateur C3834
explicite non conforme à un pointeur épingle ; Utilisez une variable locale épinglée à la place  
  
 Les casts explicites vers un pointeur épinglé ne sont pas autorisés.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3834.  
  
```  
// C3834.cpp  
// compile with: /clr  
int main() {  
   int x = 33;  
  
   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834  
   pin_ptr<int> p2 = &x;   // OK  
}  
```  
