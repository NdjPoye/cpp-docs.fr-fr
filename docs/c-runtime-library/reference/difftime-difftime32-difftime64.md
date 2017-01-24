---
title: "difftime, _difftime32, _difftime64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_difftime32"
  - "difftime"
  - "_difftime64"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_difftime64"
  - "difftime"
  - "difftime64"
  - "_difftime32"
  - "difftime32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_difftime32, fonction"
  - "difftime, fonction"
  - "time, rechercher la différence"
  - "difftime64, fonction"
  - "_difftime64, fonction"
  - "difftime32, fonction"
ms.assetid: 4cc0ac2b-fc7b-42c0-8283-8c9d10c566d0
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# difftime, _difftime32, _difftime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Recherche la différence entre deux heures.  
  
## Syntaxe  
  
```  
double difftime(   
   time_t timer1,  
   time_t timer0   
);  
double _difftime32(   
   __time32_t timer1,  
   __time32_t timer0   
);  
double _difftime64(   
   __time64_t timer1,  
   __time64_t timer0   
);  
```  
  
#### Paramètres  
 `timer1`  
 Heure de fin.  
  
 `timer0`  
 Heure de début.  
  
## Valeur de retour  
 `difftime` Renvoie le temps écoulé en secondes, à partir de `timer0` à `timer1`. La valeur retournée est un nombre à virgule flottante double précision. La valeur de retour peut être 0, indiquant une erreur.  
  
## Notes  
 Le `difftime` fonction calcule la différence entre les deux valeurs d’heure fournie `timer0` et `timer1`.  
  
 La valeur d’heure fournie doit tenir dans la plage de `time_t`.`time_t` est une valeur 64 bits. Par conséquent, la fin de la plage a été étendue à partir de 23:59:59 18 janvier 2038, UTC à 23:59:59 le 31 décembre 3000. La plage inférieure de `time_t` est toujours le 1er janvier 1970 à minuit.  
  
 `difftime` est une fonction inline qui prend la valeur soit `_difftime32` ou `_difftime64` selon que `_USE_32BIT_TIME_T` est défini. \_difftime32 et \_difftime64 peuvent être utilisés directement pour forcer l’utilisation d’une taille particulière de type au moment de la.  
  
 Ces fonctions valident leurs paramètres. Si des paramètres est égal à zéro ou négative, le Gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, ces fonctions retournent 0 et `errno` à `EINVAL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`difftime`|\<time.h\>|  
|`_difftime32`|\<time.h\>|  
|`_difftime64`|\<time.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```cpp  
// crt_difftime.c  
// This program calculates the amount of time  
// needed to do a floating-point multiply 100 million times.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
#include <float.h>  
  
double RangedRand( float range_min, float range_max)  
{  
   // Generate random numbers in the half-closed interval  
   // [range_min, range_max). In other words,  
   // range_min <= random number < range_max  
   return ((double)rand() / (RAND_MAX + 1) * (range_max - range_min)  
            + range_min);  
}  
  
int main( void )  
{  
   time_t   start, finish;  
   long     loop;  
   double   result, elapsed_time;  
   double   arNums[3];  
  
   // Seed the random-number generator with the current time so that  
   // the numbers will be different every time we run.  
   srand( (unsigned)time( NULL ) );  
  
   arNums[0] = RangedRand(1, FLT_MAX);  
   arNums[1] = RangedRand(1, FLT_MAX);  
   arNums[2] = RangedRand(1, FLT_MAX);  
   printf( "Using floating point numbers %.5e %.5e %.5e\n", arNums[0], arNums[1], arNums[2] );  
  
   printf( "Multiplying 2 numbers 100 million times...\n" );  
  
   time( &start );  
   for( loop = 0; loop < 100000000; loop++ )  
      result = arNums[loop%3] * arNums[(loop+1)%3];   
   time( &finish );  
  
   elapsed_time = difftime( finish, start );  
   printf( "\nProgram takes %6.0f seconds.\n", elapsed_time );  
}  
  
```  
  
```Output  
À l’aide de la virgule flottante aléatoire de nombres 1.04749e + 038 2.01482e + 038 1.72737e + 038Multiplying 2 à virgule flottante numéros 100 millions de fois... Programme prend 3 secondes. Nombres à virgule flottante de 2 multipliant 500 millions de fois... Programme prend 5 secondes.  
```  
  
## Équivalent .NET Framework  
 [System::DateTime::Subtract](https://msdn.microsoft.com/en-us/library/system.datetime.subtract.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)