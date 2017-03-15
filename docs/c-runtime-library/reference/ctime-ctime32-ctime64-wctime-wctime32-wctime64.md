---
title: "ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64 | Microsoft Docs"
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
  - "_ctime64"
  - "_wctime32"
  - "ctime"
  - "_wctime64"
  - "_ctime32"
  - "_wctime"
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
  - "_wctime64"
  - "_ctime32"
  - "_tctime"
  - "_wctime"
  - "_wctime32"
  - "_tctime64"
  - "_ctime64"
  - "ctime"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tctime64, fonction"
  - "_ctime32, fonction"
  - "ctime32, fonction"
  - "_wctime, fonction"
  - "wctime64, fonction"
  - "_tctime64, fonction"
  - "_tctime32, fonction"
  - "_ctime64, fonction"
  - "_wctime64, fonction"
  - "ctime, fonction"
  - "wctime32, fonction"
  - "ctime64, fonction"
  - "_wctime32, fonction"
  - "_tctime, fonction"
  - "tctime32, fonction"
  - "tctime, fonction"
  - "wctime, fonction"
  - "heure, convertir"
ms.assetid: 2423de37-a35c-4f0a-a378-3116bc120a9d
caps.latest.revision: 25
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertir une valeur d’heure en une chaîne et ajuster les paramètres de fuseau horaire local. Des versions plus sécurisées de ces fonctions sont disponibles. consultez [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md).  
  
## Syntaxe  
  
```  
char *ctime(   
   const time_t *timer   
);  
char *_ctime32(   
   const __time32_t *timer )  
;  
char *_ctime64(   
   const __time64_t *timer )  
;  
wchar_t *_wctime(   
   const time_t *timer   
);  
wchar_t *_wctime32(   
   const __time32_t *timer  
);  
wchar_t *_wctime64(   
   const __time64_t *timer   
);  
```  
  
#### Paramètres  
 `timer`  
 Pointeur vers l’heure stockée.  
  
## Valeur de retour  
 Pointeur vers le résultat de chaîne de caractères.`NULL` est renvoyée si :  
  
-   `time` représente une date antérieure au 1er janvier 1970 à minuit UTC.  
  
-   Si vous utilisez `_ctime32` ou `_wctime32` et `time` représente une date postérieure à 23:59:59 18 janvier 2038, UTC.  
  
-   Si vous utilisez `_ctime64` ou `_wctime64` et `time` représente une date postérieure à 23:59:59 le 31 décembre 3000, UTC.  
  
 `ctime` est une fonction inline qui prend la valeur `_ctime64` et `time_t` équivaut à `__time64_t`. Si vous devez forcer le compilateur à interpréter `time_t` l’ancien 32\-bit `time_t`, vous pouvez définir `_USE_32BIT_TIME_T`. Cette action provoquerait `ctime` pour prendre la valeur `_ctime32`. Cela est déconseillé, car votre application peut échouer après le 18 janvier 2038, et il n’est pas autorisée sur les plateformes 64 bits.  
  
## Notes  
 Le `ctime` fonction convertit une valeur d’heure stockée en tant qu’un [time\_t](../../c-runtime-library/standard-types.md) valeur dans une chaîne de caractères. Le `timer` valeur est généralement obtenue à partir d’un appel à [temps](../../c-runtime-library/reference/time-time32-time64.md), qui retourne le nombre de secondes écoulé depuis minuit \(00 : 00:00\), le 1er janvier 1970, temps universel \(UTC\). La chaîne de valeur de retour contient exactement 26 caractères et présente sous la forme :  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 Une horloge de 24 heures est utilisée. Tous les champs ont une largeur constante. Le caractère de saut de ligne \('\\n'\) et le caractère null \('\\0'\) occupent les deux dernières positions de la chaîne.  
  
 La chaîne de caractères convertie est également ajustée en fonction des paramètres de fuseau horaire local. Consultez le `time`, [\_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md), et [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) fonctions pour plus d’informations sur la configuration de l’heure locale et la [\_tzset](../../c-runtime-library/reference/tzset.md) \(fonction\) pour plus d’informations sur la définition de l’environnement de fuseau horaire et des variables globales.  
  
 Un appel à `ctime` modifie le tampon alloué de manière statique unique utilisé par le `gmtime` et `localtime` fonctions. Chaque appel à une de ces routines détruit le résultat de l’appel précédent.`ctime` partage d’une mémoire tampon statique avec le `asctime` \(fonction\). Par conséquent, un appel à `ctime` détruit les résultats d’un appel précédent à `asctime`, `localtime`, ou `gmtime`.  
  
 `_wctime` et `_wctime64` sont la version à caractères larges de `ctime` et `_ctime64`qui retourne un pointeur vers une chaîne à caractères larges. Dans le cas contraire, `_ctime64`, `_wctime`, et `_wctime64` se comportent de la même manière que `ctime`.  
  
 Ces fonctions valident leurs paramètres. Si `timer` est un pointeur null, ou si la valeur est négative, ces fonctions appellent le Gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, les fonctions retournent `NULL` et `errno` à `EINVAL`.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tctime`|`ctime`|`ctime`|`_wctime`|  
|`_tctime32`|`_ctime32`|`_ctime32`|`_wctime32`|  
|`_tctime64`|`_ctime64`|`_ctime64`|`_wctime64`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`ctime`|\<time.h\>|  
|`_ctime32`|\<time.h\>|  
|`_ctime64`|\<time.h\>|  
|`_wctime`|\< time.h \> ou \< wchar.h \>|  
|`_wctime32`|\< time.h \> ou \< wchar.h \>|  
|`_wctime64`|\< time.h \> ou \< wchar.h \>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_ctime64.c  
// compile with: /W3  
/* This program gets the current  
 * time in _time64_t form, then uses ctime to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   __time64_t ltime;  
  
   _time64( &ltime );  
   printf( "The time is %s\n", _ctime64( &ltime ) ); // C4996  
   // Note: _ctime64 is deprecated; consider using _ctime64_s  
}  
```  
  
```Output  
Le temps est le 13 février mercredi 16:04:43 2002  
```  
  
## Équivalent .NET Framework  
  
-   [System::DateTime::GetDateTimeFormats](https://msdn.microsoft.com/en-us/library/system.datetime.getdatetimeformats.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)