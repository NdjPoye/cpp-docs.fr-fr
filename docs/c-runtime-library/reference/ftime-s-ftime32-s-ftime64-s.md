---
title: _ftime_s, _ftime32_s, _ftime64_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ftime_s
- _ftime64_s
- _ftime32_s
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
- _ftime_s
- _ftime64_s
- ftime_s
- _ftime32_s
- ftime32_s
- ftime64_s
dev_langs:
- C++
helpviewer_keywords:
- ftime32_s function
- ftime_s function
- _ftime64_s function
- current time
- ftime64_s function
- time, getting current
- _ftime_s function
- _ftime32_s function
ms.assetid: d03080d9-a520-45be-aa65-504bdb197e8b
caps.latest.revision: 24
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 20611bb1f40ae900ad2653395da6a0d8279252db
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="ftimes-ftime32s-ftime64s"></a>_ftime_s, _ftime32_s, _ftime64_s
Obtient l’heure actuelle. Ces versions de [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) intègrent les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _ftime_s(   
   struct _timeb *timeptr   
);  
errno_t _ftime32_s(   
   struct __timeb32 *timeptr   
);  
errno_t _ftime64_s(   
   struct __timeb64 *timeptr   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `timeptr`  
 Pointeur vers un `_timeb`, `__timeb32`, ou `__timeb64` structure.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l'opération a réussi, un code d'erreur en cas d'échec. Si `timeptr` est `NULL`, la valeur de retour est `EINVAL`.  
  
## <a name="remarks"></a>Remarques  
 Le `_ftime_s` fonction obtient l’heure locale actuelle et la stocke dans la structure vers laquelle pointée `timeptr`. Le `_timeb`, `__timeb32`, et `__timeb64` structures sont définies dans SYS\Timeb.h. Elles contiennent quatre champs, qui sont présentés dans le tableau suivant.  
  
 `dstflag`  
 Valeur non nulle si l’heure d’été est en vigueur pour le fuseau horaire local. (Consultez [_tzset](../../c-runtime-library/reference/tzset.md) pour une explication de la détermination de l’heure d’été.)  
  
 `millitm`  
 Fraction de seconde en millisecondes.  
  
 `time`  
 Durée en secondes depuis le 1er janvier 1970, minuit (00:00:00), temps universel (UTC).  
  
 `timezone`  
 Différence en minutes, en direction de l’ouest, entre les heures UTC et locale. La valeur de `timezone` est définie à partir de la valeur de la variable globale `_timezone` (voir `_tzset`).  
  
 `_ftime64_s`, qui utilise la structure `__timeb64`, permet d’exprimer les dates de création de fichier jusqu’au 31 décembre 3000 à 23:59:59, heure UTC, tandis que `_ftime32_s` représente uniquement les dates jusqu’au 18 janvier 2038 à 23:59:59, heure UTC. Le 1er janvier 1970 à minuit est la limite inférieure de la plage de dates pour toutes ces fonctions.  
  
 `_ftime_s` équivaut à `_ftime64_s`, et `_timeb` contient une heure 64 bits. Cela est vrai, sauf si `_USE_32BIT_TIME_T` est défini, cas dans lequel l’ancien comportement est appliqué. `_ftime_s` utilise une heure 32 bits et `_timeb` contient une heure 32 bits.  
  
 `_ftime_s` valide ses paramètres. Si elle reçoit un pointeur null en guise de paramètre `timeptr`, la fonction appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, la fonction définit `errno` sur `EINVAL`.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`_ftime_s`|\<sys/types.h> et \<sys/timeb.h>|  
|`_ftime32_s`|\<sys/types.h> et \<sys/timeb.h>|  
|`_ftime64_s`|\<sys/types.h> et \<sys/timeb.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_ftime64_s.c  
// This program uses _ftime64_s to obtain the current  
// time and then stores this time in timebuffer.  
  
#include <stdio.h>  
#include <sys/timeb.h>  
#include <time.h>  
  
int main( void )  
{  
   struct _timeb timebuffer;  
   char timeline[26];  
   errno_t err;  
   time_t time1;  
   unsigned short millitm1;  
   short timezone1;  
   short dstflag1;  
  
   _ftime64_s( &timebuffer );  
  
    time1 = timebuffer.time;  
    millitm1 = timebuffer.millitm;  
    timezone1 = timebuffer.timezone;  
    dstflag1 = timebuffer.dstflag;  
  
   printf( "Seconds since midnight, January 1, 1970 (UTC): %I64d\n",   
   time1);  
   printf( "Milliseconds: %d\n", millitm1);  
   printf( "Minutes between UTC and local time: %d\n", timezone1);  
   printf( "Daylight savings time flag (1 means Daylight time is in "  
           "effect): %d\n", dstflag1);   
  
   err = ctime_s( timeline, 26, & ( timebuffer.time ) );  
   if (err)  
   {  
       printf("Invalid argument to ctime_s. ");  
   }  
   printf( "The time is %.19s.%hu %s", timeline, timebuffer.millitm,  
           &timeline[20] );  
}  
```  
  
```Output  
Seconds since midnight, January 1, 1970 (UTC): 1051553334  
Milliseconds: 230  
Minutes between UTC and local time: 480  
Daylight savings time flag (1 means Daylight time is in effect): 1  
The time is Mon Apr 28 11:08:54.230 2003  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
