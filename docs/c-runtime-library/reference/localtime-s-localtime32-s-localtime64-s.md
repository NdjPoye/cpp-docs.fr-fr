---
title: "localtime_s, _localtime32_s, _localtime64_s | Microsoft Docs"
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
  - "_localtime64_s"
  - "_localtime32_s"
  - "localtime_s"
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
  - "_localtime32_s"
  - "localtime32_s"
  - "localtime_s"
  - "localtime64_s"
  - "_localtime64_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_localtime64_s, fonction"
  - "localtime32_s, fonction"
  - "_localtime32_s, fonction"
  - "localtime64_s, fonction"
  - "time, convertir des valeurs"
  - "localtime_s, fonction"
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# localtime_s, _localtime32_s, _localtime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une valeur d’heure et corrige le fuseau horaire local. Voici les versions de [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) avec des améliorations de sécurité comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `_tm`  
 Pointeur vers la structure d’heure doit être renseigné.  
  
 `time`  
 Pointeur vers l’heure stockée.  
  
## Valeur de retour  
 Zéro si l’opération réussit. La valeur de retour est un code d’erreur en cas de panne. Codes d’erreur sont définies dans Errno.h. Pour obtenir la liste de ces erreurs, consultez la page [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### Conditions d’erreur  
  
|`_tm`|`time`|Valeur de retour|Valeur de `_tm`|Appelle le Gestionnaire de paramètre non valide|  
|-----------|------------|----------------------|---------------------|-----------------------------------------------------|  
|`NULL`|any|`EINVAL`|Non modifié|Oui|  
|Pas `NULL` \(pointe vers la mémoire valide\)|`NULL`|`EINVAL`|Tous les champs, la valeur \-1|Oui|  
|Pas `NULL` \(pointe vers la mémoire valide\)|inférieur à 0 ou supérieur à `_MAX__TIME64_T`|`EINVAL`|Tous les champs, la valeur \-1|Non|  
  
 Dans le cas de conditions de deux erreur première, le Gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions attribuent à `errno` la valeur `EINVAL` et retournent `EINVAL`.  
  
## Notes  
 Le `_localtime32_s` fonction convertit une heure stockée comme un [time\_t](../../c-runtime-library/standard-types.md) valeur et stocke le résultat dans une structure de type `tm`. Le `long` valeur `timer` représente les secondes écoulées depuis minuit \(00 : 00:00\), le 1er janvier 1970, UTC. Cette valeur est généralement obtenue à partir de la `time` \(fonction\).  
  
 `_localtime32_s` corrige le fuseau horaire local si l’utilisateur définit la variable d’environnement global `TZ`. Lorsque `TZ` est défini, les trois autres variables d’environnement \(`_timezone`, `_daylight`, et `_tzname`\) sont également défini automatiquement. Si le `TZ` variable n’est pas définie, `localtime32_s` tente d’utiliser les informations de fuseau horaire spécifiées dans l’application de Date\/heure dans le panneau de configuration. Si ces informations ne peut pas être obtenues, PST8PDT, ce qui signifie que le fuseau horaire Pacifique, est utilisé par défaut. Consultez la page [\_tzset](../../c-runtime-library/reference/tzset.md) pour obtenir une description de ces variables.`TZ` est une extension Microsoft ne fait pas partie de la définition de la norme ANSI de `localtime`.  
  
> [!NOTE]
>  L’environnement cible doit essayer de déterminer si l’heure d’été est en vigueur.  
  
 `_localtime64_s`, qui utilise le `__time64_t` de la structure, permet de dates d’exprimer à 23:59:59, au 31 décembre 3000, temps universel \(UTC\), tandis que `_localtime32_s` représente des dates et 23:59:59 18 janvier 2038, UTC.  
  
 `localtime_s` est une fonction inline qui prend la valeur `_localtime64_s`, et `time_t` équivaut à `__time64_t`. Si vous devez forcer le compilateur à interpréter `time_t` comme ancien `time_t` 32 bits, vous pouvez définir `_USE_32BIT_TIME_T`. Cette action provoquerait `localtime_s` pour prendre la valeur `_localtime32_s`. Cela est déconseillé, car votre application peut échouer après le 18 janvier 2038, et il n’est pas autorisée sur les plateformes 64 bits.  
  
 Les champs du type structure [tm](../../c-runtime-library/standard-types.md) stocker les valeurs suivantes, chacune d’elles étant un `int`.  
  
 `tm_sec`  
 Secondes après la minute \(0 à 59\).  
  
 `tm_min`  
 Minutes après l’heure \(0 à 59\).  
  
 `tm_hour`  
 Heures après minuit \(0\-23\).  
  
 `tm_mday`  
 Jour du mois \(1 à 31\).  
  
 `tm_mon`  
 Mois \(0 – 11 ; Janvier \= 0\).  
  
 `tm_year`  
 Year \(année en cours moins 1900\).  
  
 `tm_wday`  
 Jour de la semaine \(0\-6. Dimanche \= 0\).  
  
 `tm_yday`  
 Jour de l’année \(0 – 365 ; Le 1er janvier \= 0\).  
  
 `tm_isdst`  
 Valeur positive si l’heure d’été est en vigueur ; 0 si l’heure n’a pas d’effet ; valeur négative si l’état de l’heure d’été est inconnu. Si le `TZ` variable d’environnement est définie, la bibliothèque Runtime C part du principe que les règles appropriées aux États\-Unis pour le calcul de l’heure \(DST\).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`localtime_s`|\<time.h\>|  
|`_localtime32_s`|\<time.h\>|  
|`_localtime64_s`|\<time.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
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
  
## Résultat de l'exemple  
  
```  
Fri Apr 25 01:19:27 PM  
```  
  
## Équivalent .NET Framework  
 [System::DateTime::ToLocalTime](https://msdn.microsoft.com/en-us/library/system.datetime.tolocaltime.aspx)  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)