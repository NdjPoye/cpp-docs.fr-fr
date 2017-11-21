---
title: Compilateur avertissement (niveau 1) C4405 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4405
dev_langs: C++
helpviewer_keywords: C4405
ms.assetid: 155c64d6-58ae-4455-b61f-ccd711c5da96
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2301c85eeb91ece43cec75e4cbb2a451c27a0c8d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4405"></a>Avertissement du compilateur (niveau 1) C4405
'identificateur' : identificateur est un mot réservé  
  
 Un mot réservé pour l’assembleur inline est utilisé comme nom de variable. Cela peut entraîner des résultats imprévisibles. Pour résoudre cet avertissement, évitez d’affectation de noms de variables à des mots réservés pour l’assembleur inline. L’exemple suivant génère C4405 :  
  
```  
// C4405.cpp  
// compile with: /W1  
// processor: x86  
void func1() {  
   int mov = 0, i = 0;  
   _asm {  
      mov mov, 0;   // C4405  
      // instead, try ..  
      // mov i, 0;  
   }  
}  
  
int main() {  
}  
```