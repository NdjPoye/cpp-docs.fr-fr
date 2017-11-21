---
title: Erreur du compilateur C2227 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2227
dev_langs: C++
helpviewer_keywords: C2227
ms.assetid: d470e8b8-7e15-468b-84fa-37d1a0132271
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 57ace27f349eeb32fac0b916979c30cf2bce01c1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2227"></a>Erreur du compilateur C2227
la partie gauche de '->membre' doit pointer vers un type class/struct/union/générique  
  
 L’opérande à gauche de `->` n’est pas un pointeur vers une classe, structure ou union.  
  
 L’exemple suivant génère l’erreur C2227 :  
  
```  
// C2227.cpp  
int *pInt;  
struct S {  
public:  
    int member;  
} s, *pS = &s;  
  
int main() {  
   pInt->member = 0;   // C2227 pInt points to an int  
   pS->member = 0;   // OK  
}  
```