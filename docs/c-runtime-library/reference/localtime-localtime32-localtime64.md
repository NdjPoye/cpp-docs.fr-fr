---
title: "localtime, _localtime32, _localtime64 | Microsoft Docs"
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
  - "_localtime64"
  - "_localtime32"
  - "localtime"
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
  - "localtime64"
  - "_localtime64"
  - "localtime32"
  - "localtime"
  - "_localtime32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "localtime32, fonction"
  - "_localtime32, fonction"
  - "_localtime64, fonction"
  - "localtime64, fonction"
  - "localtime, fonction"
  - "time, convertir des valeurs"
ms.assetid: 4260ec3d-43ee-4538-b998-402a282bb9b8
caps.latest.revision: 28
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# localtime, _localtime32, _localtime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertir une valeur d’heure et la corriger le fuseau horaire local. Des versions plus sécurisées de ces fonctions sont disponibles. consultez [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md).  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `timer`  
 Pointeur vers l’heure stockée.  
  
## Valeur de retour  
 Retourner un pointeur vers le résultat de la structure, ou `NULL` Si la date est passée à la fonction est :  
  
-   Avant le 1 janvier 1970 à minuit.  
  
-   Après avoir 03:14:07, le 19 janvier 2038, UTC \(à l’aide de `_time32` et `time32_t`\).  
  
-   Après avoir 23:59:59 le 31 décembre 3000 UTC \(à l’aide de `_time64` et `__time64_t`\).  
  
 `_localtime64`, qui utilise le `__time64_t` de la structure, permet de dates d’exprimer à 23:59:59, au 31 décembre 3000, temps universel \(UTC\), tandis que `_localtime32` représente des dates et 23:59:59 18 janvier 2038, UTC.  
  
 `localtime` est une fonction inline qui prend la valeur `_localtime64`, et `time_t` équivaut à `__time64_t`. Si vous devez forcer le compilateur à interpréter `time_t`l’ancien 32\-bit `time_t`, vous pouvez définir `_USE_32BIT_TIME_T`. Cette action provoquerait `localtime` pour prendre la valeur `_localtime32`. Cela est déconseillé, car votre application peut échouer après le 18 janvier 2038, et il n’est pas autorisée sur les plateformes 64 bits.  
  
 Les champs du type structure [tm](../../c-runtime-library/standard-types.md) stocker les valeurs suivantes, chacune d’elles étant un `int`:  
  
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
  
## Notes  
 Le `localtime` fonction convertit une heure stockée comme un [time\_t](../../c-runtime-library/standard-types.md) valeur et stocke le résultat dans une structure de type `tm`. Le `long` valeur `timer` représente les secondes écoulées depuis minuit \(00 : 00:00\), le 1er janvier 1970, UTC. Cette valeur est généralement obtenue à partir de la `time` \(fonction\).  
  
 Les versions 32 bits et 64 bits de `gmtime`, `mktime`, `mkgmtime`, et `localtime` tous utiliser un seul `tm` structure par thread pour la conversion. Chaque appel à une de ces routines détruit le résultat de l’appel précédent.  
  
 `localtime` corrige le fuseau horaire local si l’utilisateur définit la variable d’environnement global `TZ`. Lorsque `TZ` est défini, les trois autres variables d’environnement \(`_timezone`, `_daylight`, et `_tzname`\) sont également défini automatiquement. Si le `TZ` variable n’est pas définie, `localtime` tente d’utiliser les informations de fuseau horaire spécifiées dans l’application de Date\/heure dans le panneau de configuration. Si ces informations ne peut pas être obtenues, PST8PDT, ce qui signifie que le fuseau horaire Pacifique, est utilisé par défaut. Consultez la page [\_tzset](../../c-runtime-library/reference/tzset.md) pour obtenir une description de ces variables.`TZ` est une extension Microsoft ne fait pas partie de la définition de la norme ANSI de `localtime`.  
  
> [!NOTE]
>  L’environnement cible doit essayer de déterminer si l’heure d’été est en vigueur.  
  
 Ces fonctions valident leurs paramètres. Si `timer` est un pointeur null, ou si la valeur est négative, ces fonctions appellent un gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, les fonctions retournent `NULL` et `errno` à `EINVAL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`localtime`|\<time.h\>|  
|`_localtime32`|\<time.h\>|  
|`_localtime64`|\<time.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
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
12 fév mar 10 h 05:58  
```  
  
## Équivalent .NET Framework  
 [System::DateTime::ToLocalTime](https://msdn.microsoft.com/en-us/library/system.datetime.tolocaltime.aspx)  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)