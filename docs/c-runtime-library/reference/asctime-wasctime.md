---
title: "asctime, _wasctime | Microsoft Docs"
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
  - "_wasctime"
  - "asctime"
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
  - "_tasctime"
  - "asctime"
  - "_wasctime"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tasctime (fonction)"
  - "_wasctime (fonction)"
  - "asctime (fonction)"
  - "tasctime (fonction)"
  - "conversion de la structure d'heure"
  - "heure, convertir"
  - "wasctime (fonction)"
ms.assetid: 974f1727-10ff-4ed4-8cac-2eb2d681f576
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# asctime, _wasctime
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une structure d'heure `tm` en une chaîne de caractères.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md).  
  
## Syntaxe  
  
```  
char *asctime(   
   const struct tm *timeptr   
);  
wchar_t *_wasctime(   
   const struct tm *timeptr   
);  
```  
  
#### Paramètres  
 `timeptr`  
 Structure Heure\/date.  
  
## Valeur de retour  
 `asctime` retourne un pointeur vers une chaîne de caractères ; `_wasctime` retourne un pointeur vers le résultat de chaîne de caractères larges.  Il n'y a pas de valeur de retour d'erreur.  
  
## Notes  
 Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md).  
  
 La fonction `asctime` convertit une heure enregistrée comme structure en une chaîne de caractères.  La valeur `timeptr` est généralement obtenue à partir d'un appel à `gmtime` ou à `localtime`, les deux retournent un pointeur vers une structure `tm`, définie dans TIME.H.  
  
|membre de timeptr|Valeur|  
|-----------------------|------------|  
|`tm_hour`|les heures depuis minuit \(0\-23\)|  
|`tm_isdst`|Positive si l'heure d'été est appliquée ; 0 si l'heure d'été n'est pas appliquée ; négatif si l'état d'heure d'été est inconnu.  La bibliothèque Runtime C suppose l'utilisation des règles des États\-Unis pour implémenter le calcul de l'heure d'été \(DST\).|  
|`tm_mday`|Le jour du mois \(1\-31\)|  
|`tm_min`|Les minutes après les heure \(0\-59\)|  
|`tm_mon`|Le mois \(0\-11 ; Janvier \= 0\)|  
|`tm_sec`|Les secondes après les minutes \(0\-59\)|  
|`tm_wday`|Jour de la semaine \(0\-6; Dimanche \= 0\)|  
|`tm_yday`|Le jour de l'année \(0\-365 ; 1er janvier \= 0\)|  
|`tm_year`|L'année \(année en cours moins 1900\)|  
  
 La chaîne de caractères convertie est également paramétrée conformément aux paramètres de fuseau horaire.  Pour des informations sur la configuration de l'heure locale, consultez les fonctions [time](../../c-runtime-library/reference/time-time32-time64.md), [\_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md), et [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md), et la fonction [\_tzset](../../c-runtime-library/reference/tzset.md) pour plus d'informations sur la définition de l'environnement des fuseaux horaires et des variables globales.  
  
 Le résultat de chaîne généré par `asctime` contient exactement 26 caractères et se présente sous la forme `Wed Jan 02 02:03:55 1980\n\0`.  Une horloge de 24 heures est utilisé.  Tous les champs ont une largeur constante.  Le nouveau caractère ligne et le caractère null occupent les deux dernières positions de la chaîne.  `asctime` utilise une mémoire tampon unique, statiquement allouée pour stocker la chaîne de retour.  Chaque appel à la fonction détruit le résultat de l'appel précédent.  
  
 `_wasctime` est une version à caractère élargi de `asctime`.  `_wasctime` et `asctime` se comportent sinon de manière identique.  
  
 Ces fonctions valident leurs paramètres.  Si `timeptr` est un pointeur null, ou s'il contient des valeurs hors limites, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, la fonction retourne `NULL` et définit `errno` à la valeur `EINVAL`.  
  
### Mappage de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tasctime`|`asctime`|`asctime`|`_wasctime`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`asctime`|\<time.h\>|  
|`_wasctime`|\<time.h\> or \<wchar.h\>|  
  
## Exemple  
 Ce programme place l'heure système dans l'entier long `aclock`, le traduit dans la structure `newtime` puis le convertit au format chaîne pour la sortie, à l'aide de la fonction `asctime`.  
  
```  
// crt_asctime.c  
// compile with: /W3  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
    struct tm   *newTime;  
    time_t      szClock;  
  
    // Get time in seconds  
    time( &szClock );  
  
    // Convert time to struct tm form   
    newTime = localtime( &szClock );  
  
    // Print local time as a string.  
    printf_s( "Current date and time: %s", asctime( newTime ) ); // C4996  
    // Note: asctime is deprecated; consider using asctime_s instead  
}  
```  
  
  **Date et heure actuelle : Dim le 3 février 11:38:58 2002**   
## Équivalent .NET Framework  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)