---
title: "ldiv, lldiv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "ldiv"
  - "lldiv"
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
  - "ldiv"
  - "lldiv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "calculer les quotients"
  - "calculer les restes"
  - "ldiv (fonction)"
  - "lldiv (fonction)"
  - "quotients, calculer"
  - "calcul des restes"
ms.assetid: 68ab5d83-27a4-479c-9d52-d055eb139eca
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# ldiv, lldiv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule le quotient et le reste de deux entiers en une opération.  
  
## Syntaxe  
  
```  
ldiv_t ldiv(  
   long numer,  
   long denom   
);  
lldiv_t lldiv(  
   long long numer,  
   long long denom   
);  
```  
  
#### Paramètres  
 `numer`  
 Numérateur  
  
 `denom`  
 Dénominateur.  
  
## Valeur de retour  
 `ldiv` retourne une structure de type [ldiv\_t](../../c-runtime-library/standard-types.md) qui comporte le quotient et le reste.  `lldiv` retourne une structure de type [lldiv\_t](../../c-runtime-library/standard-types.md) qui comporte le quotient et le reste.  
  
## Notes  
 Les fonctions `ldiv` et `lldiv` divisent `numer` par `denom` et calculent ainsi le quotient et le reste.  Le signe du quotient est identique à celui du quotient mathématique.  La valeur absolue du quotient est le plus grand entier inférieur à la valeur absolue du quotient mathématique.  Si le dénominateur est 0, le programme se termine par un message d'erreur.  `ldiv` et `lldiv` sont identiques à  `div`, sauf que les arguments de `ldiv` et les membres de la structure retournée sont de type `long`, et les arguments de `lldiv` et les membres de la structure retournée sont de type `long long`.  
  
 Les structures `ldiv_t` et `lldiv_t` sont définies dans \<stdlib.h\>.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`ldiv`, `lldiv`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_ldiv.c  
  
#include <stdlib.h>  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   long x = 5149627, y = 234879;  
   ldiv_t div_result;  
  
   div_result = ldiv( x, y );  
   printf( "For %ld / %ld, the quotient is ", x, y );  
   printf( "%ld, and the remainder is %ld\n",   
            div_result.quot, div_result.rem );  
}  
```  
  
## Sortie  
  
```  
For 5149627 / 234879, the quotient is 21, and the remainder is 217168  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [div](../../c-runtime-library/reference/div.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)