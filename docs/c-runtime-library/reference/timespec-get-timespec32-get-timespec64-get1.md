---
title: "timespec_get, _timespec32_get, _timespec64_get1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "timespec_get"
  - "_timespec32_get"
  - "_timespec64_get"
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
  - "timespec_get"
  - "_timespec32_get"
  - "_timespec64_get"
  - "time/timespec_get"
  - "time/_timespec32_get"
  - "time/_timespec64_get"
  - "timespec"
  - "_timespec32"
  - "_timespec64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "timespec_get (function)"
  - "_timespec32_get (fonction)"
  - "_timespec64_get (fonction)"
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# timespec_get, _timespec32_get, _timespec64_get
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Affecte à l’intervalle indiqué par le premier argument l’heure de calendrier actuelle, en fonction de la base de temps spécifiée.  
  
## Syntaxe  
  
```  
int timespec_get(  
    struct timespec* const time_spec,  
    int const base  
);  
int _timespec32_get(  
    struct _timespec32* const time_spec,  
    int const base  
);  
int _timespec64_get(  
    struct _timespec64* const time_spec,  
    int const base  
);  
  
```  
  
#### Paramètres  
 `time_spec`  
 Pointeur vers un struct qui a pour valeur la durée, en secondes et nanosecondes, depuis le début de l’époque.  
  
 `base`  
 Valeur propre à l’implémentation différente de zéro qui spécifie la base de temps.  
  
## Valeur de retour  
 Valeur de `base` en cas de succès. Sinon, retourne la valeur zéro.  
  
## Notes  
 Les fonctions `timespec_get` définissent l’heure actuelle dans le struct vers lequel pointe l’argument `time_spec`. Toutes les versions de ce struct ont deux membres, `tv_sec` et `tv_nsec`. La valeur `tv_sec` correspond au nombre entier de secondes et `tv_nsec` au nombre entier de nanosecondes, arrondi à la résolution de l’horloge système, depuis le début de l’époque spécifiée par `base`.  
  
 **Section spécifique à Microsoft**  
  
 Ces fonctions prennent uniquement en charge `TIME_UTC` comme valeur `base`. Affecte à la valeur `time_spec` le nombre de secondes et de nanosecondes depuis le début de l’époque, le 1er janvier 1970 à minuit UTC. Dans un `struct _timespec32`, `tv_sec` est une valeur `__time32_t`. Dans un `struct _timespec64`, `tv_sec` est une valeur `__time64_t`. Dans un `struct timespec`, `tv_sec` est un type `time_t` de longueur 32 bits ou 64 bits selon que la macro de préprocesseur \_USE\_32BIT\_TIME\_T est définie ou non. La fonction `timespec_get` est une fonction inline qui appelle `_timespec32_get` si \_USE\_32BIT\_TIME\_T est définie ; sinon, elle appelle `_timespec64_get`.  
  
 **Fin de la section spécifique à Microsoft**  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`timespec_get`, `_timespec32_get`, `_timespec64_get`|C: \<time.h\>, C\+\+: \<ctime\> or \<time.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_utime, \_utime32, \_utime64, \_wutime, \_wutime32, \_wutime64](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)