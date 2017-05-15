---
title: localtime, _localtime32, _localtime64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _localtime64
- _localtime32
- localtime
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
- localtime64
- _localtime64
- localtime32
- localtime
- _localtime32
dev_langs:
- C++
helpviewer_keywords:
- localtime32 function
- _localtime32 function
- _localtime64 function
- localtime64 function
- localtime function
- time, converting values
ms.assetid: 4260ec3d-43ee-4538-b998-402a282bb9b8
caps.latest.revision: 28
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
ms.openlocfilehash: 6dcb9a6f0d7187722a769a28cfb624e4621c181f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="localtime-localtime32-localtime64"></a>localtime, _localtime32, _localtime64
Convertissent une valeur de temps et effectuent une correction en fonction du fuseau horaire local. Des versions plus sécurisées de ces fonctions sont disponibles. Consultez [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct tm *localtime(  
   const time_t *timer   
);  
struct tm *_localtime32(  
   const __time32_t *timer  
);  
struct tm *_localtime64(  
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `timer`  
 Pointeur désignant la valeur de temps stockée.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourner un pointeur désignant le résultat de la structure, ou `NULL` si la date passée à la fonction se situe :  
  
-   Avant le 1er janvier 1970 à minuit  
  
-   Après le 19 janvier 2038 à 03:14:07, heure UTC (dans le cas de `_time32` et de `time32_t`).  
  
-   Après le 31 décembre 3000 à 23:59:59, heure UTC (dans le cas de `_time64` et de `__time64_t`).  
  
 `_localtime64`, qui utilise la structure `__time64_t`, permet d’exprimer les dates jusqu’au 31 décembre 3000 à 23:59:59, heure UTC (temps universel coordonné), tandis que `_localtime32` représente les dates jusqu’au 18 janvier 2038 à 23:59:59, heure UTC.  
  
 `localtime` est une fonction inline qui prend la valeur `_localtime64`, tandis que `time_t` équivaut à `__time64_t`. Si vous devez forcer le compilateur à interpréter `time_t` comme l’ancien `time_t` 32 bits, vous pouvez définir `_USE_32BIT_TIME_T`. Ainsi, `localtime` prend la valeur `_localtime32`. Cela n’est pas recommandé, car votre application peut échouer après le 18 janvier 2038 et cela n’est pas autorisé sur les plateformes 64 bits.  
  
 Les champs du type de structure [tm](../../c-runtime-library/standard-types.md) stockent les valeurs suivantes, chacune d’elles étant un `int` :  
  
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
  
## <a name="remarks"></a>Notes  
 La fonction `localtime` convertit une heure stockée en tant que valeur [time_t](../../c-runtime-library/standard-types.md) et stocke le résultat dans une structure de type `tm`. La valeur `long` `timer` représente les secondes écoulées depuis le 1er janvier 1970 à minuit (00:00:00), heure UTC. Cette valeur est généralement obtenue à partir de la fonction `time`.  
  
 Les versions 32 bits et 64 bits de `gmtime`, `mktime`, `mkgmtime` et `localtime` utilisent toutes une structure `tm` unique par thread pour la conversion. Chaque appel à une de ces routines détruit le résultat de l’appel précédent.  
  
 `localtime` effectue une correction en fonction du fuseau horaire local si l’utilisateur définit d’abord la variable d’environnement globale `TZ`. Quand `TZ` est définie, les trois autres variables d’environnement (`_timezone`, `_daylight` et `_tzname`) sont également définies automatiquement. Si la variable `TZ` n’est pas définie, `localtime` tente d’utiliser les informations de fuseau horaire spécifiées dans l’application Date/heure du Panneau de configuration. Si ces informations ne peuvent pas être obtenues, PST8PDT (fuseau horaire Pacifique) est utilisé par défaut. Consultez [_tzset](../../c-runtime-library/reference/tzset.md) pour obtenir une description de ces variables. `TZ` est une extension Microsoft et ne fait pas partie de la définition de la norme ANSI de `localtime`.  
  
> [!NOTE]
>  L’environnement cible doit tenter de déterminer si l’heure d’été est en vigueur.  
  
 Ces fonctions valident leurs paramètres. Si `timer` est un pointeur Null ou que la valeur d’horloge est négative, ces fonctions appellent un gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à continuer, les fonctions retournent `NULL` et définissent `errno` sur `EINVAL`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`localtime`|\<time.h>|  
|`_localtime32`|\<time.h>|  
|`_localtime64`|\<time.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_localtime.cpp  
// compile with: /W3  
/* This program uses _time64 to get the current time   
 * and then uses localtime64() to convert this time to a structure   
 * representing the local time. The program converts the result   
 * from a 24-hour clock to a 12-hour clock and determines the   
 * proper extension (AM or PM).  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <time.h>  
  
int main( void )  
{  
        struct tm *newtime;  
        char am_pm[] = "AM";  
        __time64_t long_time;  
  
        _time64( &long_time );           // Get time as 64-bit integer.  
                                         // Convert to local time.  
        newtime = _localtime64( &long_time ); // C4996  
        // Note: _localtime64 deprecated; consider _localetime64_s  
  
        if( newtime->tm_hour > 12 )        // Set up extension.  
                strcpy_s( am_pm, sizeof(am_pm), "PM" );  
        if( newtime->tm_hour > 12 )        // Convert from 24-hour  
                newtime->tm_hour -= 12;    //   to 12-hour clock.  
        if( newtime->tm_hour == 0 )        // Set hour to 12 if midnight.  
                newtime->tm_hour = 12;  
  
        char buff[30];  
        asctime_s( buff, sizeof(buff), newtime );  
        printf( "%.19s %s\n", buff, am_pm );  
}  
```  
  
```Output  
Tue Feb 12 10:05:58 AM  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)
