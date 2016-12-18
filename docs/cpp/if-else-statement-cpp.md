---
title: "if-else, instruction (C++) | Microsoft Docs"
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
  - "else_cpp"
  - "else"
  - "if_cpp"
  - "if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "else (mot clé) (C++)"
  - "if (mot clé) (C++)"
  - "if (mot clé) (C++), if-else"
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# if-else, instruction (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Contrôle le branchement conditionnel.  
  
## Syntaxe  
  
```  
  
      if ( expression )  
   statement1  
[else  
   statement2]  
```  
  
## Notes  
 Si la valeur de l'*expression* est différente de zéro, *statement1* est exécuté.  Si le **else** facultatif est présent, *statement2* est exécuté si la valeur de l'*expression* est zéro.  *l'expression* doit être arithmétiques ou de type pointeur, ou elle doit avoir un type de classe qui définit une conversion non équivoque à une arithmétique ou un type pointeur. \( Pour plus d'informations sur la conversion, consultez [Conversions standard](../cpp/standard-conversions.md). \)  
  
 Dans les deux formes de l'instruction **Si**, *l'expression*, qui peut avoir n'importe quelle valeur sauf une structure, est évaluée, y compris tous les effets secondaires.  Le contrôle passe de l'instruction **Si** à l'instruction suivante du programme à moins que l'une *des instructions*contienne un [saut](../cpp/break-statement-cpp.md), [Continuer](../cpp/continue-statement-cpp.md), ou un [goto](../cpp/goto-statement-cpp.md).  
  
 La clause **else** d'une instruction `if...else` est associée à l'instruction **Si** précédente la plus proche dans la même portée qui n'a pas d'instruction correspondante **else**.  
  
 Pour que cet exemple soit pas ambigu concernant l'accouplage `if...else`, supprimez les accolades.  
  
## Exemple  
  
```  
// if_else_statement.cpp  
#include <stdio.h>  
  
int main()   
{  
   int x = 0;  
   if (x == 0)  
   {  
      printf_s("x is 0!\n");  
   }  
   else  
   {  
      printf_s("x is not 0!\n"); // this statement will not be executed  
   }  
  
   x = 1;  
   if (x == 0)  
   {  
      printf_s("x is 0!\n"); // this statement will not be executed  
   }  
   else  
   {  
      printf_s("x is not 0!\n");  
   }  
  
   return 0;  
}  
```  
  
  **x est 0 \!**  
**x n'est pas 0 \!**   
## Voir aussi  
 [Instructions de sélection](../cpp/selection-statements-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [switch, instruction \(C\+\+\)](../cpp/switch-statement-cpp.md)