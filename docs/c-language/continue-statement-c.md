---
title: "continue, instruction (C) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "continue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "continue (mot clé) (C)"
  - "structures de boucle, continue (mot clé)"
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# continue, instruction (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'instruction `continue` passe le contrôle à l'itération suivante pour l'instruction englobante `do`, `for`, ou `while` la plus proche dans laquelle elle apparaît, en ignorant toutes les instructions restantes dans le corps de l'instruction `do`, `for`, ou `while`.  
  
## Syntaxe  
 `jump-statement`:  
 `continue;`  
  
 L'itération suivante pour une instruction `do`, `for`, ou `while` est déterminée comme suit :  
  
-   Dans une instruction `do` ou `while`, l'itération suivante démarre en réévaluant l'expression de l'instruction `do` ou `while`.  
  
-   Une instruction `continue` dans une instruction `for` provoque l'expression en boucle de l'instruction `for` à évaluer.  Ensuite le compilateur réévalue l'expression conditionnelle et, selon le résultat, termine ou itère le corps de l'instruction.  Consultez [L'instruction for](../c-language/for-statement-c.md) pour plus d'informations sur l'instruction `for` et ses non terminaux.  
  
 Voici un exemple d'instruction `continue` :  
  
```  
while ( i-- > 0 )   
{  
    x = f( i );  
    if ( x == 1 )  
        continue;  
    y += x * x;  
}  
```  
  
 Dans cet exemple, le corps de l'instruction est exécuté alors que `i` est supérieur à 0.  Le premier `f(i)` est assigné à `x` ; ensuite, si `x` est égal à 1, l'instruction `continue` est exécutée.  Le reste des instructions du corps sont ignorées, et l'exécution se poursuit en haut de la boucle avec l'évaluation du test de boucle.  
  
## Voir aussi  
 [continue, instruction](../cpp/continue-statement-cpp.md)