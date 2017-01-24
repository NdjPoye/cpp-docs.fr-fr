---
title: "continue, instruction (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "continue"
  - "continue_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "continue (mot clé) (C++)"
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# continue, instruction (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Force le transfert de contrôle sur l'expression de contrôle de la plus petite boucle [do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md) ou [while](../cpp/while-statement-cpp.md) englobante.  
  
## Syntaxe  
  
```  
continue;  
```  
  
## Notes  
 Toutes les instructions restantes dans l'itération actuelle ne sont pas exécutées.  L'itération suivante de la boucle est déterminée comme suit :  
  
-   Dans une boucle `do` ou `while`, l'itération suivante démarre en réévaluant l'expression de contrôle de l'instruction `do` ou `while`.  
  
-   Dans une boucle `for` \(utilisant la syntaxe `for`\(`init-expr`; `cond-expr`; `loop-expr`\)\), la clause `loop-expr` est exécutée.  Ensuite la clause `cond-expr` est réévaluée et, selon le résultat, la boucle se termine ou une autre itération a lieu.  
  
 L'exemple suivant montre comment l'instruction `continue` peut être utilisée pour ignorer les sections de code et démarrer l'itération suivante d'une boucle.  
  
## Exemple  
  
```  
// continue_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        i++;  
        printf_s("before the continue\n");  
        continue;  
        printf("after the continue, should never print\n");  
     } while (i < 3);  
  
     printf_s("after the do loop\n");  
}  
```  
  
  **avant l'instruction continue**  
**avant l'instruction continue**  
**avant l'instruction continue**  
**après la boucle do**   
## Voir aussi  
 [Instructions de saut](../cpp/jump-statements-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)