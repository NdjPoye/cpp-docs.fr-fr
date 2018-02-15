---
title: clock | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- clock
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- clock
dev_langs:
- C++
helpviewer_keywords:
- processor time used, calculating
- time, calculating processor
- clock function
- processor time used
- calculating processor time used
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d56f29f1693fba1f4b455d8ae80ee38603e3a604
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="clock"></a>horloge
Calcule le temps horloge utilisé par le processus appelant.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
clock_t clock( void );  
```  
  
## <a name="return-value"></a>Valeur de retour  
Temps écoulé depuis l’initialisation du CRT au début du processus, mesuré en `CLOCKS_PER_SEC` unités par seconde. Si le temps écoulé n’est pas disponible ou a dépassé le délai positif maximal qui peut être enregistré en tant que type `clock_t`, la fonction retourne la valeur `(clock_t)(-1)`.   
  
## <a name="remarks"></a>Notes  
La fonction `clock` indique combien de temps horloge s’est écoulé depuis l’initialisation du CRT pendant le processus de démarrage. Notez que cette fonction n’est pas strictement conforme à la norme ISO C, selon laquelle le temps processeur net est spécifié par la valeur de retour. Pour obtenir les temps processeur, utilisez la fonction Win32 [GetProcessTimes](https://msdn.microsoft.com/library/windows/desktop/ms683223). Pour déterminer le temps écoulé en secondes, divisez la valeur retournée par la fonction `clock` par la macro `CLOCKS_PER_SEC`.  
  
Selon la durée écoulée, la valeur retournée par `clock` peut dépasser la valeur positive maximale de `clock_t`. Quand le processus s’exécute plus longtemps, la valeur retournée par `clock` est toujours `(clock_t)(-1)`, tel que spécifié par les normes ISO C99 (7.23.2.1) et ISO C11 (7.27.2.1). Microsoft implémente `clock_t` en tant que `long`, entier signé 32 bits, et la macro `CLOCKS_PER_SEC` est définie avec la valeur 1000. Cela donne pour la fonction `clock` une valeur de retour maximale de 2 147 483,647 secondes ou 24,8 jours environ. Ne vous fiez pas à la valeur retournée par `clock` dans les processus qui durent plus longtemps que cet intervalle de temps. Vous pouvez utiliser la fonction `time` 64 bits ou la fonction Windows [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904) pour enregistrer des durées de processus couvrant plusieurs années.  

## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`clock`|\<time.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_clock.c  
// This sample uses clock() to 'sleep' for three 
// seconds, then determines how long it takes  
// to execute an empty loop 600000000 times.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
  
// Pauses for a specified number of milliseconds.  
void do_sleep( clock_t wait )  
{  
   clock_t goal;  
   goal = wait + clock();  
   while( goal > clock() )  
      ;  
}  
  
const long num_loops = 600000000L;

int main( void )  
{  
   long    i = num_loops;  
   clock_t start, finish;  
   double  duration;  
  
   // Delay for a specified time.  
   printf( "Delay for three seconds\n" );  
   do_sleep( (clock_t)3 * CLOCKS_PER_SEC );  
   printf( "Done!\n" );  
  
   // Measure the duration of an event.  
   start = clock();  
   while( i-- )   
      ;  
   finish = clock();  
   duration = (double)(finish - start) / CLOCKS_PER_SEC;  
   printf( "Time to do %ld empty loops is ", num_loops );  
   printf( "%2.3f seconds\n", duration );  
}  
```  
  
```Output  
Delay for three seconds  
Done!  
Time to do 600000000 empty loops is 1.354 seconds  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [difftime, _difftime32, _difftime64](../../c-runtime-library/reference/difftime-difftime32-difftime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)