---
title: "break, instruction (C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "break"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "break (mot clé) (C)"
ms.assetid: 015627c7-0924-49b2-a4d1-c77edf5eae6a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# break, instruction (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'instruction `break` termine l'exécution de l'instruction `do`, `for`, `switch` ou `while` englobante la plus proche dans laquelle elle figure.  Le contrôle est transmis à l'instruction qui suit l'instruction terminée.  
  
## Syntaxe  
 *jump\-statement* :  
 `break;`  
  
 L'instruction `break` est fréquemment utilisée pour mettre fin au traitement d'un cas particulier dans une instruction `switch`.  L'absence d'une instruction itérative ou `switch` englobante génère une erreur.  
  
 Dans les instructions imbriquées, l'instruction `break` met un terme uniquement à l'instruction `do`, `for`, `switch` ou `while` qui l'englobe immédiatement.  Vous pouvez utiliser une instruction `return` ou `goto` pour transférer le contrôle hors de la structure imbriquée.  
  
 L'exemple suivant illustre l'instruction `break` :  
  
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
  
## Voir aussi  
 [break, instruction](../cpp/break-statement-cpp.md)