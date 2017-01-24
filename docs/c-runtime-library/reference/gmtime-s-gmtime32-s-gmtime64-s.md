---
title: "gmtime_s, _gmtime32_s, _gmtime64_s | Microsoft Docs"
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
  - "_gmtime32_s"
  - "gmtime_s"
  - "_gmtime64_s"
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
  - "_gmtime_s"
  - "gmtime64_s"
  - "gmtime32_s"
  - "_gmtime64_s"
  - "gmtime_s"
  - "_gmtime32_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "gmtime_s (fonction)"
  - "gmtime32_s (fonction)"
  - "fonctions d'heure"
  - "gmtime64_s (fonction)"
  - "_gmtime64_s (fonction)"
  - "conversion de la structure d'heure"
  - "_gmtime_s (fonction)"
  - "_gmtime32_s (fonction)"
ms.assetid: 261c7df0-2b0c-44ba-ba61-cb83efaec60f
caps.latest.revision: 29
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# gmtime_s, _gmtime32_s, _gmtime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une valeur d’heure en une structure. Voici les versions de [\_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) avec des améliorations de sécurité comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t gmtime_s(  
   struct tm* _tm,  
   const __time_t* time  
);  
errno_t _gmtime32_s(  
   struct tm* _tm,  
   const __time32_t* time  
);  
errno_t _gmtime64_s(  
   struct tm* _tm,  
   const __time64_t* time   
);  
```  
  
#### Paramètres  
 `_tm`  
 Pointeur vers un `tm` structure. Les champs de la structure renvoyée doit contenir la valeur évaluée de la `timer` argument UTC plutôt qu’en heure locale.  
  
 `time`  
 Pointeur vers l’heure stockée. L’heure est représentée comme secondes écoulées depuis minuit \(00 : 00:00\), le 1er janvier 1970, temps universel \(UTC\).  
  
## Valeur de retour  
 Zéro si l’opération réussit. La valeur de retour est un code d’erreur en cas de panne. Codes d’erreur sont définies dans Errno.h ; Pour obtenir la liste de ces erreurs, consultez la page [errno](../../c-runtime-library/errno-constants.md).  
  
### Conditions d’erreur  
  
|`_tm`|`time`|Retourner|Valeur de `_tm`|  
|-----------|------------|---------------|---------------------|  
|`NULL`|any|`EINVAL`|Non modifié.|  
|Pas `NULL` \(pointe vers la mémoire valide\)|`NULL`|`EINVAL`|Tous les champs de la valeur \-1.|  
|Pas `NULL`|\< 0|`EINVAL`|Tous les champs de la valeur \-1.|  
  
 Dans le cas de conditions de deux erreur première, le Gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions attribuent à `errno` la valeur `EINVAL` et retournent `EINVAL`.  
  
## Notes  
 Le `_gmtime32_s` fonction décompose le `time` valeur et la stocke dans une structure de type `tm`, défini dans Time.h. L’adresse de la structure est passée dans `_tm`. La valeur de `time` est généralement obtenue à partir d’un appel à la `time` \(fonction\).  
  
> [!NOTE]
>  L’environnement cible doit essayer de déterminer si l’heure d’été est en vigueur. La bibliothèque Runtime C suppose que les règles des États\-Unis pour le calcul de l’heure d’été.  
  
 Les champs de la structure sont de type `int`, comme indiqué dans le tableau suivant.  
  
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
  
 `_gmtime64_s`, qui utilise le `__time64_t` de la structure, permet d’exprimer à 23:59:59 le 31 décembre 3000 UTC ; des dates tandis que `gmtime32_s` représentent uniquement les dates et 23:59:59 18 janvier 2038, UTC. Minuit, le 1er janvier 1970, est la limite inférieure de la plage de dates pour ces deux fonctions.  
  
 `gmtime_s` est une fonction inline qui prend la valeur `_gmtime64_s` et `time_t` équivaut à `__time64_t`. Si vous devez forcer le compilateur à interpréter `time_t` comme ancien `time_t` 32 bits, vous pouvez définir `_USE_32BIT_TIME_T`. Cette action provoquerait `gmtime_s` être inline avec `_gmtime32_s`. Cela est déconseillé, car votre application peut échouer après le 18 janvier 2038, et il n’est pas autorisée sur les plateformes 64 bits.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`gmtime_s`|\<time.h\>|  
|`_gmtime32_s`|\<time.h\>|  
|`_gmtime64_s`|\<time.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_gmtime64_s.c  
// This program uses _gmtime64_s to convert a 64-bit  
// integer representation of coordinated universal time  
// to a structure named newtime, then uses asctime_s to  
// convert this structure to an output string.  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm newtime;  
   __int64 ltime;  
   char buf[26];  
   errno_t err;  
  
   _time64( &ltime );  
  
   // Obtain coordinated universal time:   
   err = _gmtime64_s( &newtime, &ltime );  
   if (err)  
   {  
      printf("Invalid Argument to _gmtime64_s.");  
   }  
  
   // Convert to an ASCII representation   
   err = asctime_s(buf, 26, &newtime);  
   if (err)  
   {  
      printf("Invalid Argument to asctime_s.");  
   }  
  
   printf( "Coordinated universal time is %s\n",   
           buf );  
}  
```  
  
```Output  
Temps universel coordonné est le 25 avril vendredi 12:20:33 2003  
```  
  
## Équivalent .NET Framework  
  
-   [System::DateTime::UtcNow](https://msdn.microsoft.com/en-us/library/system.datetime.utcnow.aspx)  
  
-   [System::DateTime::ToUniversalTime](https://msdn.microsoft.com/en-us/library/system.datetime.touniversaltime.aspx)  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [\_mkgmtime, \_mkgmtime32, \_mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)