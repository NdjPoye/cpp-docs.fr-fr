---
title: gmtime, _gmtime32, _gmtime64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _gmtime32
- gmtime
- _gmtime64
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
- gmtime
- _gmtime32
- _gmtime64
dev_langs:
- C++
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4646902145796ede0659493cb0805cfdf85bb52e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="gmtime-gmtime32-gmtime64"></a>gmtime, _gmtime32, _gmtime64
Convertit une valeur de temps en une structure. Des versions plus sécurisées de ces fonctions sont disponibles. Consultez [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct tm *gmtime(   
   const time_t *timer   
);  
struct tm *_gmtime32(   
   const __time32_t *timer   
);  
struct tm *_gmtime64(   
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `timer`  
 Pointeur désignant la valeur de temps stockée. Le temps est représenté sous forme de secondes écoulées depuis le 1er janvier 1970 minuit (00:00:00), temps universel coordonné (UTC).  
  
## <a name="return-value"></a>Valeur de retour  
 Pointeur désignant une structure de type [tm](../../c-runtime-library/standard-types.md). Les champs de la structure retournée doivent contenir la valeur évaluée de l’argument `timer` en heure UTC plutôt qu’en heure locale. Chacun des champs de la structure est de type `int`, comme suit :  
  
 `tm_sec`  
 Secondes après la minute (0 - 59).  
  
 `tm_min`  
 Minutes après l’heure (0 - 59).  
  
 `tm_hour`  
 Heures écoulées depuis minuit (0 - 23).  
  
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
 Toujours 0 pour `gmtime`.  
  
 Les versions 32 bits et 64 bits de `gmtime`, `mktime`, `mkgmtime` et `localtime` utilisent toutes une structure `tm` commune par thread pour la conversion. Chaque appel à une de ces fonctions détruit le résultat de tout appel précédent. Si `timer` représente une date antérieure au 1er janvier 1970 à minuit, `gmtime` retourne `NULL`. Aucun retour d'erreur.  
  
 `_gmtime64`, qui utilise la structure `__time64_t`, permet d’exprimer les dates jusqu’au 31 décembre 3000 à 23:59:59, heure UTC, tandis que `_gmtime32` représente uniquement les dates jusqu’au 18 janvier 2038 à 23:59:59, heure UTC. Le 1er janvier 1970 à minuit est la limite inférieure de la plage de dates pour les deux fonctions.  
  
 `gmtime` est une fonction inline qui prend la valeur `_gmtime64`, tandis que `time_t` équivaut à `__time64_t` sauf si `_USE_32BIT_TIME_T` est défini. Si vous devez forcer le compilateur à interpréter `time_t` comme l’ancien `time_t` 32 bits, vous pouvez définir `_USE_32BIT_TIME_T`, mais ce faisant `gmtime` se retrouve inline avec `_gmtime32`, et `time_t` doit être défini en tant que `__time32_t`. Nous vous recommandons de ne pas effectuer cette opération, car elle n’est pas autorisée sur les plateformes 64 bits et, dans tous les cas, votre application risque d’échouer après le 18 janvier 2038.  
  
 Ces fonctions valident leurs paramètres. Si `timer` est un pointeur Null ou que la valeur d’horloge est négative, ces fonctions appellent un gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à continuer, les fonctions retournent `NULL` et définissent `errno` sur `EINVAL`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_gmtime32` décompose la valeur `timer` et la stocke dans une structure allouée de manière statique de type `tm`, définie dans le TIME.H. La valeur de `timer` est généralement obtenue à partir d’un appel à la fonction `time`.  
  
> [!NOTE]
>  Dans la plupart des cas, l’environnement cible tente de déterminer si l’heure d’été est en vigueur. La bibliothèque runtime C suppose que les règles de calcul de l’heure d’été utilisées sont celles des États-Unis.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`gmtime`|\<time.h>|  
|`_gmtime32`|\<time.h>|  
|`_gmtime64`|\<time.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```C  
// crt_gmtime.c  
// compile with: /W3  
// This program uses _gmtime64 to convert a long-  
// integer representation of coordinated universal time  
// to a structure named newtime, then uses asctime to  
// convert this structure to an output string.  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm *newtime;  
   __int64 ltime;  
   char buff[80];  
  
   _time64( &ltime );  
  
   // Obtain coordinated universal time:  
   newtime = _gmtime64( &ltime ); // C4996  
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s  
   asctime_s( buff, sizeof(buff), newtime );  
   printf( "Coordinated universal time is %s\n", buff );  
}  
```  
  
```Output  
Coordinated universal time is Tue Feb 12 23:11:31 2002  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [_mkgmtime, _mkgmtime32, _mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)