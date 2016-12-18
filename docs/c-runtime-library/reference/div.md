---
title: "div | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "div"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "div"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "div (fonction)"
  - "diviser des entiers"
  - "quotients"
  - "quotients, calculer"
  - "calcul des restes"
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# div
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule le quotient et le reste de deux valeurs entières.  
  
## Syntaxe  
  
```  
div_t div(   
   int numer,  
   int denom   
);  
ldiv_t div(  
   long numer,  
   long denom  
); /* C++ only */   
lldiv_t div(  
   long long numer,  
   long long denom  
); /* C++ only */  
```  
  
#### Paramètres  
 `numer`  
 Le numérateur.  
  
 `denom`  
 Le dénominateur.  
  
## Valeur de retour  
 `div` appelée en utilisant des arguments de type `int` retourne une structure du type `div_t`, qui comporte le quotient et le reste.  La valeur de retour de surcharge avec des arguments de type `long` est `ldiv_t`.  `div_t` et `ldiv_t` sont définis dans STDLIB.H.  
  
## Notes  
 La fonction `div` divise `numer` par `denom` et calcule ainsi le quotient et le reste.  La structure [div\_t](../../c-runtime-library/standard-types.md) contient le quotient, `int``quot`, et le reste, `int` `rem`.  Le signe du quotient est identique à celui du quotient mathématique.  Sa valeur absolue est le plus grand entier inférieur à la valeur absolue du quotient mathématique.  Si le dénominateur est 0, le programme se termine par un message d'erreur.  
  
 Les surcharges qui acceptent des arguments de type `long` ou `long long` sont uniquement disponibles au code C\+\+.  Le type de retour [ldiv\_t](../../c-runtime-library/standard-types.md) contient des membres `long` `quot` et `long``rem`, et le type de retour [lldiv\_t](../../c-runtime-library/standard-types.md) contient des membres `long long quot` et `long long rem`, qui ont les mêmes significations que les membres de `div_t`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`div`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_div.c  
// arguments: 876 13  
  
// This example takes two integers as command-line  
// arguments and displays the results of the integer  
// division. This program accepts two arguments on the  
// command line following the program name, then calls  
// div to divide the first argument by the second.  
// Finally, it prints the structure members quot and rem.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <math.h>  
  
int main( int argc, char *argv[] )  
{  
   int x,y;  
   div_t div_result;  
  
   x = atoi( argv[1] );  
   y = atoi( argv[2] );  
  
   printf( "x is %d, y is %d\n", x, y );  
   div_result = div( x, y );  
   printf( "The quotient is %d, and the remainder is %d\n",  
           div_result.quot, div_result.rem );  
}  
```  
  
  **x est 876, y est 13**  
**Le quotient est 67, et le reste est 5**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)