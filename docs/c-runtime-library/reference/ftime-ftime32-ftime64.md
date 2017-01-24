---
title: "_ftime, _ftime32, _ftime64 | Microsoft Docs"
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
  - "_ftime64"
  - "_ftime"
  - "_ftime32"
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
  - "_ftime32"
  - "_ftime"
  - "_ftime64"
  - "ftime64"
  - "ftime"
  - "ftime32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ftime64, fonction"
  - "_ftime64, fonction"
  - "heure actuelle"
  - "_ftime, fonction"
  - "ftime, fonction"
  - "_ftime32, fonction"
  - "ftime32, fonction"
  - "heure, obtenir actuelle"
ms.assetid: 96bc464c-3bcd-41d5-a212-8bbd836b814a
caps.latest.revision: 27
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ftime, _ftime32, _ftime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient l'heure actuelle.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md).  
  
## Syntaxe  
  
```  
void _ftime(   
   struct _timeb *timeptr   
);  
void _ftime32(   
   struct __timeb32 *timeptr   
);  
void _ftime64(   
   struct __timeb64 *timeptr   
);  
```  
  
#### Paramètres  
 `timeptr`  
 Pointeur vers une structure `_timeb`,`__timeb32` ou `__timeb64` .  
  
## Notes  
 La fonction `_ftime` obtient l'heure locale actuelle et la stocke dans la structure désignée par `timeptr`*.* Les structures `_timeb`, `__timeb32`,et`__timeb64` sont définies dans SYS\\Timeb.h.  Ils contiennent quatre champs, répertoriés dans le tableau suivant.  
  
 `dstflag`  
 Une valeur différente de zéro si l'heure d'été est actuellement en vigueur pour le fuseau horaire local. \(Voir [\_tzset](../../c-runtime-library/reference/tzset.md) pour obtenir des explications sur la manière dont l'heure d'été est déterminée.\)  
  
 `millitm`  
 Fraction de seconde en millisecondes.  
  
 `time`  
 Durée en secondes depuis minuit \(0h00 : 00\), le 1er janvier 1970, temps universel coordonné \(UTC\).  
  
 `timezone`  
 Différence en minutes, en se déplaçant vers l'ouest, entre UTC et l'heure locale.  La valeur `timezone` est définie à partir de la valeur de la variable globale `_timezone` \(voir `_tzset`\).  
  
 `_ftime64`qui utilise la structure `__timeb64`, permet que les dates de création de fichiers soient exprimés jusqu'à 23:59:59, le 31 décembre, 3000, UTC ; alors que `_ftime32` représente uniquement les dates jusqu'à 03:14:07 Le 19 janvier, 2038, UTC.  Minuit, le 1er janvier 1970, est la limite inférieure de la plage de dates pour ces deux fonctions.  
  
 `_ftime` équivaut à `_ftime64` et `_timeb` contient une heure 64 bits.  Ceci s'applique à moins que `_USE_32BIT_TIME_T` ne soit défini, auquel cas le comportement antérieur est appliqué ; `_ftime` utilise une heure 32 bits et `_timeb` contient une heure 32 bits.  
  
 `_ftime` valide ses paramètres.  Si `timeptr` est un pointeur null, la fonction appelle le gestionnaire de paramètres invalides comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, la fonction retourne \-1 et définit `errno` avec la valeur `EINVAL`.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_ftime`|\<système\/types.h et\> système \<\/timeb.h\>|  
|`_ftime32`|\<système\/types.h et\> système \<\/timeb.h\>|  
|`_ftime64`|\<système\/types.h et\> système \<\/timeb.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_ftime.c  
// compile with: /W3  
// This program uses _ftime to obtain the current  
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
  
   _ftime( &timebuffer ); // C4996  
   // Note: _ftime is deprecated; consider using _ftime_s instead  
  
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
  
  **Secondes depuis minuit, le 1er janvier 1970 \(UTC\) : 1051553334**  
**Millisecondes:230**  
**Minutes entre UTC et l'heure locale : 480**  
**Indicateur heure d'été \(1 heure d'été l'authentification est appliquée\) : 1**  
**L'heure est mois le 28 avril 11 : 08:54.230 2003**   
## Équivalent .NET Framework  
 [System.DateTime](https://msdn.microsoft.com/en-us/library/system.datetime.now.aspx)  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)