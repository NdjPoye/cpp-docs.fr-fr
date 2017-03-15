---
title: "gmtime, _gmtime32, _gmtime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_gmtime32"
  - "gmtime"
  - "_gmtime64"
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
  - "gmtime"
  - "_gmtime32"
  - "_gmtime64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_gmtime32 (fonction)"
  - "_gmtime64 (fonction)"
  - "gmtime (fonction)"
  - "gmtime32 (fonction)"
  - "gmtime64 (fonction)"
  - "fonctions d'heure"
  - "conversion de la structure d'heure"
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# gmtime, _gmtime32, _gmtime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une valeur d’heure en une structure. Des versions plus sécurisées de ces fonctions sont disponibles. consultez [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md).  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `timer`  
 Pointeur vers l’heure stockée. L’heure est représentée comme secondes écoulées depuis minuit \(00 : 00:00\), le 1er janvier 1970, temps universel \(UTC\).  
  
## Valeur de retour  
 Un pointeur vers une structure de type [tm](../../c-runtime-library/standard-types.md). Les champs de la structure renvoyée doit contenir la valeur évaluée de la `timer` argument UTC plutôt qu’en heure locale. Les champs de la structure sont de type `int`, comme suit :  
  
 `tm_sec`  
 Secondes après la minute \(0 à 59\).  
  
 `tm_min`  
 Minutes après l’heure \(0 à 59\).  
  
 `tm_hour`  
 Heures écoulées depuis minuit \(0\-23\).  
  
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
 Toujours 0 pour `gmtime`.  
  
 Les versions 32 bits et 64 bits de `gmtime`, `mktime`, `mkgmtime`, et `localtime` utilisent tous un commun `tm` structure par thread pour la conversion. Chaque appel à une de ces fonctions détruit le résultat d’un appel précédent. Si `timer` représente une date antérieure au 1er janvier 1970 à minuit `gmtime` renvoie `NULL`. Aucun retour d'erreur.  
  
 `_gmtime64`, qui utilise le `__time64_t` structure, Active les dates d’exprimer à 23:59:59 le 31 décembre 3000 UTC, tandis que `_gmtime32` représentent uniquement les dates et 23:59:59 18 janvier 2038, UTC. Minuit, le 1er janvier 1970, est la limite inférieure de la plage de dates pour les deux fonctions.  
  
 `gmtime` est une fonction inline qui prend la valeur `_gmtime64`, et `time_t` équivaut à `__time64_t` sauf si `_USE_32BIT_TIME_T` est défini. Si vous devez forcer le compilateur à interpréter `time_t` l’ancien 32\-bit `time_t`, vous pouvez définir `_USE_32BIT_TIME_T`, mais ainsi, `gmtime` être inline avec `_gmtime32` et `time_t` doit être défini comme `__time32_t`. Nous recommandons que vous ne le faites pas, car il n’est pas autorisée sur les plateformes 64 bits et dans tous les cas, votre application peut échouer après le 18 janvier 2038.  
  
 Ces fonctions valident leurs paramètres. Si `timer` est un pointeur null, ou si la valeur est négative, ces fonctions appellent un gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, les fonctions retournent `NULL` et `errno` à `EINVAL`.  
  
## Notes  
 Le `_gmtime32` fonction décompose le `timer` valeur et la stocke dans une structure allouée de manière statique de type `tm`, défini dans le temps. H. La valeur de `timer` est généralement obtenue à partir d’un appel à la `time` \(fonction\).  
  
> [!NOTE]
>  Dans la plupart des cas, l’environnement cible tente de déterminer si l’heure d’été est en vigueur. La bibliothèque Runtime C suppose que les règles des États\-Unis pour implémenter le calcul de l’heure d’été \(DST\) sont utilisés.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`gmtime`|\<time.h\>|  
|`_gmtime32`|\<time.h\>|  
|`_gmtime64`|\<time.h\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
  
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
Temps universel coordonné est le 12 fév mar 11:23:31 2002  
```  
  
## Équivalent .NET Framework  
  
-   [System::DateTime::UtcNow](https://msdn.microsoft.com/en-us/library/system.datetime.utcnow.aspx)  
  
-   [System::DateTime::ToUniversalTime](https://msdn.microsoft.com/en-us/library/system.datetime.touniversaltime.aspx)  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [\_mkgmtime, \_mkgmtime32, \_mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)