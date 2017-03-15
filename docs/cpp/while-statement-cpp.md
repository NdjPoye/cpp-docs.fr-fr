---
title: "while, instruction (C++) | Microsoft Docs"
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
  - "while_cpp"
  - "while"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "while (mot clé C++)"
  - "while (mot clé C++), syntaxe"
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# while, instruction (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Exécute *l'instruction* à plusieurs reprises jusqu'à ce que *l'expression* corresponde à zéro.  
  
## Syntaxe  
  
```  
  
      while ( expression )  
   statement  
```  
  
## Notes  
 Le test de *l'expression* a lieu avant chaque exécution de la boucle, toutefois une boucle `while` est exécutée plusieurs fois ou pas du tout.  *l'expression* doit être de type intégral, de type pointeur, ou d'un type de classe avec une conversion non équivoque à une intégrale ou un type pointeur.  
  
 Une boucle `while` peut également se terminer lorsqu'une instruction [break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md) ou [return](../cpp/return-statement-cpp.md) est exécutée dans le corps de l'instruction.  Utilisez [Continuer](../cpp/continue-statement-cpp.md) pour terminer l'itération actuelle sans quitter la boucle `while`.  **continue** passe le contrôle à l'itération suivante de la boucle `while`.  
  
 Le code suivant utilise une boucle `while` pour supprimer des traits de soulignement de fin d'une chaîne :  
  
```  
// while_statement.cpp  
  
#include <string.h>  
#include <stdio.h>  
char *trim( char *szSource )  
{  
    char *pszEOS = 0;  
  
    //  Set pointer to character before terminating NULL  
    pszEOS = szSource + strlen( szSource ) - 1;  
  
    //  iterate backwards until non '_' is found   
    while( (pszEOS >= szSource) && (*pszEOS == '_') )  
        *pszEOS-- = '\0';  
  
    return szSource;  
}  
int main()  
{  
    char szbuf[] = "12345_____";  
  
    printf_s("\nBefore trim: %s", szbuf);  
    printf_s("\nAfter trim: %s\n", trim(szbuf));  
}  
```  
  
 L'état d'arrêt est évalué en haut de la boucle.  S'il n'existe aucun trait de soulignement de fin, la boucle ne s'exécute jamais.  
  
## Voir aussi  
 [Instructions d'itération](../cpp/iteration-statements-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [do\-while, instruction \(C\+\+\)](../cpp/do-while-statement-cpp.md)   
 [for, instruction \(C\+\+\)](../cpp/for-statement-cpp.md)   
 [Basé sur une plage, instruction \(C\+\+\)](../cpp/range-based-for-statement-cpp.md)