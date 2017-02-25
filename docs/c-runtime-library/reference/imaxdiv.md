---
title: "imaxdiv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "imaxdiv"
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
  - "imaxdiv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "imaxdiv (fonction)"
ms.assetid: 7d90126f-fdc2-4986-9cdf-94e4c9123d26
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# imaxdiv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule le quotient et le reste de deux valeurs entières de n'importe quelle taille en une seule opération.  
  
## Syntaxe  
  
```  
imaxdiv_t imaxdiv(   
   intmax_t numer,  
   intmax_t denom   
);   
```  
  
#### Paramètres  
 `numer`  
 Le numérateur.  
  
 `denom`  
 Le dénominateur.  
  
## Valeur de retour  
 `imaxdiv` appelé avec des arguments de type [intmax\_t](../../c-runtime-library/standard-types.md) retourne une structure de type [imaxdiv\_t](../../c-runtime-library/standard-types.md) qui comporte le quotient et le reste.  
  
## Notes  
 La fonction `imaxdiv` divise `numer` par `denom` et calcule ainsi le quotient et le reste.  La structure `imaxdiv_t` contient le quotient, `intmax_t`, `quot`, et le reste, `intmax_t` `rem`.  Le signe du quotient est identique à celui du quotient mathématique.  Sa valeur absolue est le plus grand entier inférieur à la valeur absolue du quotient mathématique.  Si le dénominateur est 0, le programme se termine par un message d'erreur.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`imaxdiv`|\<inttypes.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_imaxdiv.c  
// Build using: cl /W3 /Tc crt_imaxdiv.c  
// This example takes two integers as command-line  
// arguments and calls imaxdiv to divide the first   
// argument by the second, then displays the results.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <inttypes.h>  
  
int main(int argc, char *argv[])  
{  
   intmax_t x,y;  
   imaxdiv_t div_result;  
  
   x = atoll(argv[1]);  
   y = atoll(argv[2]);  
  
   printf("The call to imaxdiv(%lld, %lld)\n", x, y);  
   div_result = imaxdiv(x, y);  
   printf("results in a quotient of %lld, and a remainder of %lld\n\n",  
          div_result.quot, div_result.rem);  
}  
```  
  
 Lorsqu'il est généré et appelé à l'aide des paramètres de ligne de commande de `9460730470000000 8766`, le code génère la sortie suivante :  
  
  **L'appel à imaxdiv\(9460730470000000, 8766\)**  
**résultats dans un quotient de 1079252848505 et un reste de 5170**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [div](../../c-runtime-library/reference/div.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)