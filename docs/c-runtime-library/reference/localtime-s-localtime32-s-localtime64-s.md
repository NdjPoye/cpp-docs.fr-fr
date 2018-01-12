---
title: localtime_s, _localtime32_s, _localtime64_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _localtime64_s
- _localtime32_s
- localtime_s
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
- _localtime32_s
- localtime32_s
- localtime_s
- localtime64_s
- _localtime64_s
dev_langs: C++
helpviewer_keywords:
- _localtime64_s function
- localtime32_s function
- _localtime32_s function
- localtime64_s function
- time, converting values
- localtime_s function
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ddce7d73919e7e7942d8ddd7954ce6cbec4789fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="localtimes-localtime32s-localtime64s"></a>localtime_s, _localtime32_s, _localtime64_s
Convertit une valeur de temps et effectue une correction en fonction du fuseau horaire local. Ces versions de [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) intègrent les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t localtime_s(  
   struct tm* _tm,  
   const time_t *time   
);  
errno_t _localtime32_s(  
   struct tm* _tm,  
   const time32_t *time   
);  
errno_t _localtime64_s(  
   struct tm* _tm,  
   const _time64_t *time   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `_tm`  
 Pointeur désignant la structure de temps à renseigner.  
  
 `time`  
 Pointeur désignant la valeur de temps stockée.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l’opération réussit. En cas d’échec, la valeur de retour est un code d’erreur. Les codes d’erreur sont définis dans Errno.h. Pour obtenir la liste de ces erreurs, consultez [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`_tm`|`time`|Valeur de retour|Valeur dans `_tm`|Appelle un gestionnaire de paramètres non valides|  
|-----------|------------|------------------|--------------------|---------------------------------------|  
|`NULL`|any|`EINVAL`|Non modifiée|Oui|  
|Pas `NULL` (pointe vers une mémoire valide)|`NULL`|`EINVAL`|Tous les champs définis sur -1|Oui|  
|Pas `NULL` (pointe vers une mémoire valide)|Inférieur à 0 ou supérieur à `_MAX__TIME64_T`|`EINVAL`|Tous les champs définis sur -1|Non|  
  
 Concernant les deux premières conditions d’erreur, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions attribuent à `errno` la valeur `EINVAL` et retournent `EINVAL`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_localtime32_s` convertit une heure stockée en tant que valeur [time_t](../../c-runtime-library/standard-types.md) et stocke le résultat dans une structure de type `tm`. La valeur `long` `timer` représente les secondes écoulées depuis le 1er janvier 1970 à minuit (00:00:00), heure UTC. Cette valeur est généralement obtenue à partir de la fonction `time`.  
  
 `_localtime32_s` effectue une correction en fonction du fuseau horaire local si l’utilisateur définit d’abord la variable d’environnement globale `TZ`. Quand `TZ` est définie, les trois autres variables d’environnement (`_timezone`, `_daylight` et `_tzname`) sont également définies automatiquement. Si la variable `TZ` n’est pas définie, `localtime32_s` tente d’utiliser les informations de fuseau horaire spécifiées dans l’application Date/heure du Panneau de configuration. Si ces informations ne peuvent pas être obtenues, PST8PDT (fuseau horaire Pacifique) est utilisé par défaut. Consultez [_tzset](../../c-runtime-library/reference/tzset.md) pour obtenir une description de ces variables. `TZ` est une extension Microsoft et ne fait pas partie de la définition de la norme ANSI de `localtime`.  
  
> [!NOTE]
>  L’environnement cible doit tenter de déterminer si l’heure d’été est en vigueur.  
  
 `_localtime64_s`, qui utilise la structure `__time64_t`, permet d’exprimer les dates jusqu’au 18 janvier 3001 à 23:59:59,, heure UTC (temps universel coordonné), tandis que `_localtime32_s` représente les dates jusqu’au 18 janvier 2038 à 23:59:59, heure UTC.  
  
 `localtime_s` est une fonction inline qui prend la valeur `_localtime64_s`, tandis que `time_t` équivaut à `__time64_t`. Si vous devez forcer le compilateur à interpréter `time_t` comme ancien `time_t`32 bits, vous pouvez définir `_USE_32BIT_TIME_T`. Ainsi, `localtime_s` prend la valeur `_localtime32_s`. Cela n’est pas recommandé, car votre application peut échouer après le 18 janvier 2038 et cela n’est pas autorisé sur les plateformes 64 bits.  
  
 Les champs du type de structure [tm](../../c-runtime-library/standard-types.md) stockent les valeurs suivantes, chacune d’elles étant un `int`.  
  
 `tm_sec`  
 Secondes après la minute (0 - 59).  
  
 `tm_min`  
 Minutes après l’heure (0 - 59).  
  
 `tm_hour`  
 Heures après minuit (0 - 23).  
  
 `tm_mday`  
 Jour du mois (1 à 31).  
  
 `tm_mon`  
 Mois (0 - 11 ; Janvier = 0).  
  
 `tm_year`  
 Année (année en cours moins 1900).  
  
 `tm_wday`  
 Jour de la semaine (0 - 6 ; Dimanche = 0).  
  
 `tm_yday`  
 Jour de l’année (0 - 365 ; Le 1er janvier = 0).  
  
 `tm_isdst`  
 Valeur positive si l’heure d’été est en vigueur ; 0 si l’heure d’été n’est pas appliquée ; valeur négative si l’état de l’heure d’été est inconnu. Si la variable d’environnement `TZ` est définie, la bibliothèque runtime C suppose que les règles de calcul de l’heure d’été appropriées sont celles des États-Unis.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`localtime_s`|\<time.h>|  
|`_localtime32_s`|\<time.h>|  
|`_localtime64_s`|\<time.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_localtime_s.c  
/* This program uses _time64 to get the current time   
 * and then uses _localtime64_s() to convert this time to a structure   
 * representing the local time. The program converts the result   
 * from a 24-hour clock to a 12-hour clock and determines the   
 * proper extension (AM or PM).  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <time.h>  
  
int main( void )  
{  
        struct tm newtime;  
        char am_pm[] = "AM";  
        __time64_t long_time;  
        char timebuf[26];  
        errno_t err;  
  
        // Get time as 64-bit integer.  
        _time64( &long_time );   
        // Convert to local time.  
        err = _localtime64_s( &newtime, &long_time );   
        if (err)  
        {  
            printf("Invalid argument to _localtime64_s.");  
            exit(1);  
        }  
        if( newtime.tm_hour > 12 )        // Set up extension.   
                strcpy_s( am_pm, sizeof(am_pm), "PM" );  
        if( newtime.tm_hour > 12 )        // Convert from 24-hour   
                newtime.tm_hour -= 12;    // to 12-hour clock.   
        if( newtime.tm_hour == 0 )        // Set hour to 12 if midnight.  
                newtime.tm_hour = 12;  
  
        // Convert to an ASCII representation.   
        err = asctime_s(timebuf, 26, &newtime);  
        if (err)  
        {  
           printf("Invalid argument to asctime_s.");  
           exit(1);  
        }  
        printf( "%.19s %s\n", timebuf, am_pm );  
}  
```  
  
## <a name="sample-output"></a>Résultat de l'exemple  
  
```  
Fri Apr 25 01:19:27 PM  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)
