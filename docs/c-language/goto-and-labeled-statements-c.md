---
title: "Instructions goto et &#233;tiquet&#233;es (C) | Microsoft Docs"
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
  - "goto"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "goto (mot clé) (C)"
  - "labeled (instruction)"
  - "instructions, labeled"
ms.assetid: 3d0473dc-4b18-4fcc-9616-31a38499d7d7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Instructions goto et &#233;tiquet&#233;es (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'instruction `goto` transfère le contrôle à une étiquette.  L'étiquette donnée doit résider dans la même fonction et peut apparaître devant une seule instruction dans la même fonction.  
  
## Syntaxe  
 *statement*:  
 *labeled\-statement*  
  
 *jump\-statement*  
  
 *jump\-statement*:  
 **goto**  *identifier*  **;**  
  
 *labeled\-statement*:  
 *identifier*  **:**  *statement*  
  
 Une étiquette d'instruction est uniquement explicite pour une instruction `goto`. Dans tout autre contexte, une instruction étiquetée est exécutée sans tenir compte de l'étiquette.  
  
 *jump\-statement*doit résider dans la même fonction et peut apparaître devant une seule instruction dans la même fonction.  L'ensemble des noms *identifier* suivant une instruction `goto` a son propre espace de noms et les noms n'interfèrent donc pas avec d'autres identificateurs.  Les étiquettes ne peuvent pas être redéclarées.  Pour plus d'informations, consultez [Espaces de noms](../c-language/name-spaces.md).  
  
 Il est toutefois conseillé d'utiliser l'instruction **break**, **continue** et `return` plutôt que `goto` dans la mesure du possible.  Étant donné que l'instruction **break** n'exécute une sortie que d'un niveau de la boucle, une instruction `goto` peut être nécessaire pour quitter une boucle dans une boucle profondément imbriquée.  
  
 Cet exemple illustre l'instruction `goto` :  
  
```  
// goto.c  
#include <stdio.h>  
  
int main()  
{  
    int i, j;  
  
    for ( i = 0; i < 10; i++ )  
    {  
        printf_s( "Outer loop executing. i = %d\n", i );  
        for ( j = 0; j < 3; j++ )  
        {  
            printf_s( " Inner loop executing. j = %d\n", j );  
            if ( i == 5 )  
                goto stop;  
        }  
    }  
  
    /* This message does not print: */  
    printf_s( "Loop exited. i = %d\n", i );  
  
    stop: printf_s( "Jumped to stop. i = %d\n", i );  
}  
```  
  
 Dans cet exemple, une instruction `goto` transfère le contrôle au point étiqueté `stop` lorsque `i` est égal à 5.  
  
## Voir aussi  
 [Instructions](../c-language/statements-c.md)