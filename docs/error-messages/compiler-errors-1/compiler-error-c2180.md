---
title: Erreur du compilateur C2180 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2180
dev_langs:
- C++
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 181309cca171c872a7c3767729a755d6e73bd288
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2180"></a>Erreur du compilateur C2180
l'expression de contrôle a le type 'type'  
  
 L'expression de contrôle dans une instruction `if`, `while`, `for` ou `do` est une expression convertie vers `void`. Pour résoudre ce problème, remplacez l'expression de contrôle par une expression qui génère un `bool` ou un type pouvant être converti en `bool`.  
  
 L'exemple suivant génère l'erreur C2180 :  
  
```  
// C2180.c  
  
int main() {  
   while ((void)1)   // C2180  
      return 1;  
   while (1)         // OK  
      return 0;  
}  
```
