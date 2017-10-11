---
title: Erreur du compilateur C2563 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2563
dev_langs:
- C++
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8fe3ca54a90b91151288076fd657752e3195e318
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2563"></a>Erreur du compilateur C2563
incompatibilité dans la liste de paramètres formels  
  
 La liste de paramètres formels d’une fonction (ou un pointeur vers une fonction) ne correspond pas à ceux d’une autre fonction (ou pointeur vers une fonction membre). Par conséquent, l’attribution des fonctions ou des pointeurs n’est pas possible.  
  
 L’exemple suivant génère l’erreur C2563 :  
  
```  
// C2563.cpp  
void func( int );  
void func( int, int );  
int main() {  
   void *fp();  
   fp = func;   // C2563  
}  
```
