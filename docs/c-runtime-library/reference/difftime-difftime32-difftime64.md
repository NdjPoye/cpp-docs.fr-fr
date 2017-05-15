---
title: difftime, _difftime32, _difftime64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _difftime32
- difftime
- _difftime64
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
- _difftime64
- difftime
- difftime64
- _difftime32
- difftime32
dev_langs:
- C++
helpviewer_keywords:
- _difftime32 function
- difftime function
- time, finding the difference
- difftime64 function
- _difftime64 function
- difftime32 function
ms.assetid: 4cc0ac2b-fc7b-42c0-8283-8c9d10c566d0
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: f6ab058a86a5635aa341c964644a291f61ba170b
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="difftime-difftime32-difftime64"></a>difftime, _difftime32, _difftime64
Recherche la différence entre deux heures.  
  
## <a name="syntax"></a>Syntaxe  
  
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
  
#### <a name="parameters"></a>Paramètres  
 `timer1`  
 Heure de fin  
  
 `timer0`  
 Heure de début  
  
## <a name="return-value"></a>Valeur de retour  
 `difftime` retourne le temps écoulé en secondes, entre `timer0` et `timer1`. La valeur retournée est un nombre à virgule flottante double précision. Cette valeur peut être 0, indiquant alors une erreur.  
  
## <a name="remarks"></a>Notes  
 La fonction `difftime` calcule la différence entre les deux valeurs de temps `timer0` et `timer1` fournies.  
  
 La valeur de temps fournie doit appartenir à la plage `time_t`. `time_t` est une valeur 64 bits. Ainsi, la fin de la plage a été repoussée du 18 janvier 2038 à 23:59:59, heure UTC au 31 décembre 3000 à 23:59:59. Le début de la plage de `time_t` est toujours le 1er janvier 1970 à minuit.  
  
 `difftime` est une fonction inline qui prend la valeur `_difftime32` ou `_difftime64` selon que `_USE_32BIT_TIME_T` est défini. _difftime32 et _difftime64 peuvent être utilisés directement pour forcer l’utilisation d’une taille particulière du type d’heure.  
  
 Ces fonctions valident leurs paramètres. Si l’un des paramètres est zéro ou négatif, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, ces fonctions retournent 0 et définissent `errno` avec la valeur `EINVAL`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`difftime`|\<time.h>|  
|`_difftime32`|\<time.h>|  
|`_difftime64`|\<time.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
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
Using random floating point numbers 1.04749e+038 2.01482e+038 1.72737e+038Multiplying 2 floating point numbers 100 million times...Program takes      3 seconds.Multiplying 2 floating point numbers 500 million times...  
  
Program takes      5 seconds.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
