---
title: Instruction break (C) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- break
dev_langs:
- C++
helpviewer_keywords:
- break keyword [C]
ms.assetid: 015627c7-0924-49b2-a4d1-c77edf5eae6a
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 994f4b82a95fa6db187f35da63450775642bdf68
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="break-statement-c"></a>break, instruction (C)
L'instruction `break` termine l'exécution de l'instruction `do`, `for`, `switch` ou `while` englobante la plus proche dans laquelle elle figure. Le contrôle est transmis à l'instruction qui suit l'instruction terminée.  
  
## <a name="syntax"></a>Syntaxe  
 *saut-instruction* :  
 `break;`  
  
 L'instruction `break` est fréquemment utilisée pour mettre fin au traitement d'un cas particulier dans une instruction `switch`. L'absence d'une instruction itérative ou `switch` englobante génère une erreur.  
  
 Dans les instructions imbriquées, l'instruction `break` met un terme uniquement à l'instruction `do`, `for`, `switch` ou `while` qui l'englobe immédiatement. Vous pouvez utiliser une instruction `return` ou `goto` pour transférer le contrôle hors de la structure imbriquée.  
  
 L'exemple suivant illustre l'instruction `break` :  
  
```  
#include <stdio.h>  
int main() {  
   char c;  
   for(;;) {  
      printf_s( "\nPress any key, Q to quit: " );  
  
      // Convert to character value  
      scanf_s("%c", &c);  
      if (c == 'Q')  
          break;  
   }  
} // Loop exits only when 'Q' is pressed  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Instruction break](../cpp/break-statement-cpp.md)
