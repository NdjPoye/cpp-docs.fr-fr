---
title: "horloge | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "clock"
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
  - "clock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "calculer le temps processeur utilisé"
  - "clock (fonction)"
  - "temps processeur utilisé"
  - "temps processeur utilisé, calculer"
  - "heure, calculer le processeur"
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# horloge
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule le temps horloge utilisé par le processus appelant.  
  
## Syntaxe  
  
```  
clock_t clock( void );  
```  
  
## Valeur de retour  
 Temps horloge écoulé depuis le démarrage du processus \(temps écoulé en secondes multiplié par `CLOCKS_PER_SEC`\).  Si le temps écoulé n'est pas disponible, la fonction retourne – 1, converti en `clock_t`.  
  
## Notes  
 La fonction `clock` indique la quantité de temps horloge que le processus appelant a utilisée.  Notez que cela n'est pas strictement conforme à la norme ISO C99, selon laquelle le temps processeur net est spécifié par la valeur de retour.  Pour obtenir le temps processeur, utilisez la fonction Win32 [GetProcessTimes](http://msdn.microsoft.com/library/windows/desktop/ms683223).  
  
 Un cycle d'horloge est d'environ \/`CLOCKS_PER_SEC` secondes.  Avec le temps, la valeur retournée par `clock` peut dépasser la valeur positive maximale de `clock_t` et devenir négative, voire dépasser la valeur absolue maximale avant d'être renouvelée.  Ne vous fiez pas à cette valeur de temps total écoulé dans les processus qui s'exécutent pendant plus de 214 748 secondes, soit environ 59 heures.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`clock`|\<time.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_clock.c  
// This example prompts for how long  
// the program is to run and then continuously  
// displays the elapsed time for that period.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
  
void sleep( clock_t wait );  
  
int main( void )  
{  
   long    i = 6000000L;  
   clock_t start, finish;  
   double  duration;  
  
   // Delay for a specified time.  
   printf( "Delay for three seconds\n" );  
   sleep( (clock_t)3 * CLOCKS_PER_SEC );  
   printf( "Done!\n" );  
  
   // Measure the duration of an event.  
   printf( "Time to do %ld empty loops is ", i );  
   start = clock();  
   while( i-- )   
      ;  
   finish = clock();  
   duration = (double)(finish - start) / CLOCKS_PER_SEC;  
   printf( "%2.1f seconds\n", duration );  
}  
  
// Pauses for a specified number of milliseconds.  
void sleep( clock_t wait )  
{  
   clock_t goal;  
   goal = wait + clock();  
   while( goal > clock() )  
      ;  
}  
```  
  
  **Delay for three seconds**  
**Done\!  Time to do 6000000 empty loops is 0.1 seconds**    
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [difftime, \_difftime32, \_difftime64](../../c-runtime-library/reference/difftime-difftime32-difftime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)