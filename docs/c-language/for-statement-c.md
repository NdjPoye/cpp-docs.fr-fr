---
title: "for, instruction (C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "for (mot clé) (C)"
ms.assetid: 560a8de4-19db-4868-9f18-dbe51b17900d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# for, instruction (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'instruction `for` vous permet de répéter une instruction ou une instruction composée un nombre de fois spécifié.  Le corps d'une instruction `for` est exécuté zéro ou plusieurs fois jusqu'à ce qu'une condition facultative ait la valeur false.  Vous pouvez utiliser des expressions facultatives dans l'instruction `for` pour initialiser et modifier des valeurs pendant l'exécution de l'instruction `for`.  
  
## Syntaxe  
 *instruction\-itération* :  
 `for` \( `init-expression` option ; `cond-expression`option ; `loop-expression` option \)`statement`  
  
 L'exécution d'une instruction `for` continue comme suit :  
  
1.  `init-expression`, le cas échéant, est évalué.  Cela spécifie l'initialisation de la boucle.  Il n'existe aucune restriction sur le type d'`init-expression`.  
  
2.  `cond-expression`, le cas échéant, est évalué.  Cette expression doit avoir un type arithmétique ou pointeur.  Elle est évaluée avant chaque itération.  Trois résultats sont possibles :  
  
    -   Si `cond-expression` a la valeur true \(différente de zéro\), `statement` est exécuté. Ensuite `loop-expression`, le cas échéant, est évalué.  The `loop-expression` est évalué après chaque itération.  Il n'existe aucune restriction sur son type.  Les effets secondaires s'exécuteront dans l'ordre.  Le processus commence ensuite de nouveau avec l'évaluation de `cond-expression`.  
  
    -   Si `cond-expression` est omis, `cond-expression` est considéré comme true, et l'exécution reprend exactement comme décrit dans le paragraphe précédent.  Une instruction `for` sans argument `cond-expression` se termine uniquement lorsqu'une instruction `break` ou `return` dans le corps d'instruction est exécutée ou lorsqu'une instruction `goto` \(vers une instruction étiquetée extérieure au corps d'instruction `for`\) est exécutée.  
  
    -   Si `cond-expression` a la valeur `false` \(0\), l'exécution de l'instruction `for` se termine et le contrôle passe à l'instruction suivante du programme.  
  
 Une instruction `for` se termine également lorsqu'une instruction `break`, `goto` ou `return` appartenant au corps d'instruction est exécutée.  Une instruction `continue` dans une boucle `for` entraîne l'évaluation de `loop-expression`.  Lorsqu'une instruction `break` est exécutée dans une boucle `for`, `loop-expression` n'est ni évalué, ni exécuté.  Cette instruction  
  
```  
for( ;; )  
```  
  
 est la méthode courante pour produire une boucle infinie qui ne peut être quittée qu'avec une instruction `break`, `goto`, ou `return`.  
  
## Code  
 L'exemple suivant illustre l'instruction `for` :  
  
```  
// c_for.c  
int main()  
{  
   char* line = "H e  \tl\tlo World\0";  
   int space = 0;  
   int tab = 0;  
   int i;  
   int max = strlen(line);  
   for (i = 0; i < max; i++ )   
   {  
      if ( line[i] == ' ' )  
      {  
          space++;  
      }  
      if ( line[i] == '\t' )  
      {  
          tab++;  
      }  
   }  
  
   printf("Number of spaces: %i\n", space);  
   printf("Number of tabs: %i\n", tab);  
   return 0;  
}  
```  
  
## Sortie  
  
```  
Number of spaces: 4  
Number of tabs: 2  
```  
  
## Voir aussi  
 [Instructions](../c-language/statements-c.md)