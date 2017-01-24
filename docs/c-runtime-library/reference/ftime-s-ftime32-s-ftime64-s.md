---
title: "_ftime_s, _ftime32_s, _ftime64_s | Microsoft Docs"
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
  - "_ftime_s"
  - "_ftime64_s"
  - "_ftime32_s"
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
  - "_ftime_s"
  - "_ftime64_s"
  - "ftime_s"
  - "_ftime32_s"
  - "ftime32_s"
  - "ftime64_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ftime32_s, fonction"
  - "ftime_s, fonction"
  - "_ftime64_s, fonction"
  - "heure actuelle"
  - "ftime64_s, fonction"
  - "heure, obtenir actuelle"
  - "_ftime_s, fonction"
  - "_ftime32_s, fonction"
ms.assetid: d03080d9-a520-45be-aa65-504bdb197e8b
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ftime_s, _ftime32_s, _ftime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient l’heure actuelle. Voici les versions de [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) avec des améliorations de sécurité comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `timeptr`  
 Pointeur vers un `_timeb,``__timeb32`, ou `__timeb64` structure.  
  
## Valeur de retour  
 Zéro si l’opération réussit, un code d’erreur en cas d’échec. Si `timeptr` est `NULL`, la valeur de retour est `EINVAL`.  
  
## Notes  
 Le `_ftime_s` fonction obtient l’heure locale actuelle et le stocke dans la structure vers laquelle pointée `timeptr`*.* Le `_timeb,``__timeb32`,et`__timeb64` structures sont définies dans SYS\\Timeb.h. Elles contiennent quatre champs, qui sont répertoriées dans le tableau suivant.  
  
 `dstflag`  
 Différent de zéro si l’heure d’été est actuellement en vigueur pour le fuseau horaire local. \(Voir [\_tzset](../../c-runtime-library/reference/tzset.md) pour une explication de la détermination de l’heure d’été.\)  
  
 `millitm`  
 Fraction de seconde en millisecondes.  
  
 `time`  
 Durée en secondes écoulées depuis minuit \(00 : 00:00\), le 1er janvier 1970, temps universel \(UTC\).  
  
 `timezone`  
 Différence en minutes, le déplacement de westward, heure UTC et l’heure locale. La valeur de `timezone` est définie à partir de la valeur de la variable globale `_timezone` \(voir `_tzset`\).  
  
 `_ftime64_s`, qui utilise le `__timeb64` de la structure, autorise les dates de création de fichiers d’exprimer à 23:59:59 le 31 décembre 3000 UTC ; alors que `_ftime32_s` représente uniquement les dates et 23:59:59 18 janvier 2038, UTC. Minuit, le 1er janvier 1970, est la limite inférieure de la plage de dates pour toutes ces fonctions.  
  
 `_ftime_s` est équivalent à `_ftime64_s` et `_timeb` contient une heure de 64 bits. Cela est vrai, sauf si \_`USE_32BIT_TIME_T` est défini, auquel cas l’ancien comportement est en vigueur ; \_`ftime_s` utilise une durée de 32 bits et `_timeb` contient une heure de 32 bits.  
  
 `_ftime_s` valide ses paramètres. Si passé un pointeur null en tant que `timeptr`, la fonction appelle le Gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, la fonction définit `errno` à `EINVAL`.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_ftime_s`|\< sys\/types.h \> et \< sys\/timeb.h \>|  
|`_ftime32_s`|\< sys\/types.h \> et \< sys\/timeb.h \>|  
|`_ftime64_s`|\< sys\/types.h \> et \< sys\/timeb.h \>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
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
Secondes écoulées depuis minuit, le 1er janvier 1970 (UTC) : 1051553334 millisecondes : 230 Minutes entre l’heure UTC et l’heure locale : 480 heure indicateur (1 signifie l’heure d’été est en vigueur) : 1 le temps est 11:08:54.230 mois le 28 avril 2003  
```  
  
## Équivalent .NET Framework  
 [System::DateTime::Now](https://msdn.microsoft.com/en-us/library/system.datetime.now.aspx)  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)