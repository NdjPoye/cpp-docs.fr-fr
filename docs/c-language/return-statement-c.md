---
title: "return, instruction (C) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "( ) parenthèses dans les instructions de retour"
ms.assetid: 18cd82cf-f899-4b28-83ad-4eff353ddcb4
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# return, instruction (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'instruction `return` met fin à l'exécution d'une fonction et retourne le contrôle à la fonction d'appel.  L'exécution se poursuit dans la fonction d'appel au point immédiatement après l'appel.  Une instruction `return` peut également retourner une valeur à la fonction d'appel.  Pour plus d'informations, consultez le type de retour [](../c-language/return-type.md "Return Type").  
  
## Syntaxe  
 *jump\-statement*:  
 **return**  *expression*  opt **;**  
  
 La valeur de l' *expression*, si cette dernière est présente, est retournée à la fonction d'appel.  Si l'*expression* est omise, la valeur de retour de la fonction n'est pas définie.  L'expression, le cas échéant, est évaluée puis convertie au type retourné par la fonction.  Si la fonction est déclarée avec un type de retour `void`, une instruction `return` contenant une expression génère un avertissement et l'expression n'est pas évaluée.  
  
 Si aucune instruction `return` n'apparaît dans une définition de fonction, le contrôle retourne automatiquement à la fonction d'appel après que la dernière instruction de la fonction appelée est exécutée.  Dans ce cas, la valeur de retour de la fonction appelée n'est pas définie.  Une valeur de retour n'est pas obligatoire, cependant il faut déclarer la fonction pour avoir le type de retour de `void` ; sinon, le type de retour par défaut est `int`.  
  
 De nombreux programmeurs utilisent des parenthèses pour joindre l'argument *d'expression* de l'instruction `return`.  Toutefois, C ne requiert pas de parenthèses.  
  
 L'instruction `return` est illustrée dans cet exemple :  
  
```  
#include <limits.h>  
#include <stdio.h>  
  
void draw( int i, long long ll );  
long long sq( int s );  
  
int main()  
{  
    long long y;  
    int x = INT_MAX;  
  
    y = sq( x );  
    draw( x, y );  
    return x;  
}  
  
long long sq( int s )  
{  
    // Note that parentheses around the return expression   
    // are allowed but not required here.  
    return( s * (long long)s );  
}  
  
void draw( int i, long long ll )  
{  
    printf( "i = %d, ll = %lld\n", i, ll );  
    return;  
}  
  
```  
  
 Dans cet exemple, la fonction `main` appelle deux fonctions : `sq` et `draw`.  La fonction `sq` retourne la valeur d'`x * x` à `main`, où la valeur de retour est assignée à `y`.  Les parenthèses autour de l'expression de retour dans `sq` sont évaluées dans le cadre de l'expression, et ne sont pas requises par l'instruction de retour.  Puisque l'expression de retour est évaluée avant d'être convertie au type de retour, `sq` force le type d'expression à être le type de retour avec un transtypage pour éviter un possible dépassement sur les entiers, qui peut provoquer des résultats inattendus.  La fonction `draw` est déclarée comme fonction `void`.  Elle imprime les valeurs de ses paramètres et l'instruction de retour vide termine la fonction et ne retourne pas de valeur.  Tenter d'assigner la valeur de retour de `draw` engendrerait un message de diagnostic à publier.  La fonction `main` retourne la valeur d'`x` au système d'exploitation.  
  
 La sortie de l'exemple se présente comme suit :  
  
  **i \= 2147483647, ll \= 4611686014132420609**   
## Voir aussi  
 [Instructions](../c-language/statements-c.md)