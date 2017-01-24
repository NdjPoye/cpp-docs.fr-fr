---
title: "do-while, instruction (C++) | Microsoft Docs"
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
  - "do-while_cpp"
  - "do-while"
  - "do"
  - "while_cpp"
  - "do_cpp"
  - "while"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "do (mot clé C++)"
  - "do (mot clé C++), do-while"
  - "do-while (mot clé C++)"
  - "while (mot clé C++), do-while"
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# do-while, instruction (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Exécute un *statement* à plusieurs reprises jusqu'à ce que la condition d'arrêt spécifiée \(l'élément *expression*\) corresponde à zéro.  
  
## Syntaxe  
  
```  
  
      do  
   statement  
   while ( expression ) ;  
```  
  
## Notes  
 Le test de la condition d'arrêt est effectué après chaque exécution de la boucle ; par conséquent, une boucle `do-while` s'exécute une ou plusieurs fois, selon la valeur de l'expression d'arrêt.  L'instruction `do-while` peut également se terminer lorsqu'une instruction [break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md) ou [return](../cpp/return-statement-cpp.md) est exécutée dans le corps de l'instruction.  
  
 L'élément *expression* doit être de type arithmétique ou pointeur.  L'exécution se déroule comme suit :  
  
1.  Le corps de l'instruction est exécuté.  
  
2.  Ensuite, l'élément *expression* est évalué.  Si l'élément *expression* est false, l'instruction `do-while` se termine et le contrôle passe à l'instruction suivante du programme.  Si l'élément *expression* est true \(différent de zéro\), le processus se répète, en commençant à l'étape 1.  
  
## Exemple  
 L'exemple suivant illustre l'instruction `do-while` :  
  
```  
// do_while_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        printf_s("\n%d",i++);  
    } while (i < 3);  
}  
```  
  
## Voir aussi  
 [Instructions d'itération](../cpp/iteration-statements-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [while, instruction \(C\+\+\)](../cpp/while-statement-cpp.md)   
 [for, instruction \(C\+\+\)](../cpp/for-statement-cpp.md)   
 [Basé sur une plage, instruction \(C\+\+\)](../cpp/range-based-for-statement-cpp.md)