---
title: "_mkgmtime, _mkgmtime32, _mkgmtime64 | Microsoft Docs"
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
  - "_mkgmtime32"
  - "_mkgmtime64"
  - "_mkgmtime"
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
  - "_mkgmtime64"
  - "mkgmtime32"
  - "_mkgmtime32"
  - "mkgmtime"
  - "mkgmtime64"
  - "_mkgmtime"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "mkgmtime32 (fonction)"
  - "fonctions d'heure"
  - "mkgmtime (fonction)"
  - "_mkgmtime (fonction)"
  - "convertir des heures"
  - "mkgmtime64 (fonction)"
  - "_mkgmtime64 (fonction)"
  - "_mkgmtime32 (fonction)"
  - "heure, convertir"
ms.assetid: b4ca2b67-e198-4f43-b3e2-e8ad6bd01867
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mkgmtime, _mkgmtime32, _mkgmtime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une heure UTC représentée par une `tm``struct` pour une heure UTC représentée par un `time_t` type.  
  
## Syntaxe  
  
```  
  
time_t _mkgmtime(  
   struct tm*   
timeptr  
);  
__time32_t _mkgmtime32(  
   struct tm*   
timeptr  
);  
__time64_t _mkgmtime64(  
   struct tm*   
timeptr  
);  
  
```  
  
#### Paramètres  
 `timeptr`  
 Un pointeur vers l’heure UTC comme un `struct``tm` à convertir.  
  
## Valeur de retour  
 Une quantité de type `__time32_t` ou `__time64_t` qui représente le nombre de secondes écoulées depuis minuit, le 1er janvier 1970, en temps universel coordonné \(UTC\). Si la date est hors limites \(voir la section Notes\) ou l’entrée ne peut pas être interprétée comme une heure valide, la valeur de retour sera \-1.  
  
## Notes  
 Le `_mkgmtime32` et `_mkgmtime64` fonctions convertissent un horaire UTC un `__time32_t` ou `__time64_t` type qui représente l’heure UTC. Pour convertir une heure locale en heure UTC, utilisez `mktime`, `_mktime32`, et `_mktime64` à la place.  
  
 `_mkgmtime` est une fonction inline qui prend la valeur `_mkgmtime64`, et `time_t` équivaut à `__time64_t`. Si vous devez forcer le compilateur à interpréter `time_t`l’ancien 32\-bit `time_t`, vous pouvez définir `_USE_32BIT_TIME_T`. Cela n’est pas recommandée, car votre application risque d’échouer après le 18 janvier 2038 \(la plage maximale de 32 bits `time_t`\), et il n’est pas autorisé à tout sur des plateformes 64 bits.  
  
 Le temps passée structure changera, procédez comme suit dans la même façon lorsqu’elles sont modifiées avec le `_mktime` fonctions : le `tm_wday` et `tm_yday` champs sont définis sur les nouvelles valeurs en fonction des valeurs de `tm_mday` et `tm_year`. Au moment de spécifier une heure de structure `tm`, affectez au champ `tm_isdst` l'une des valeurs suivantes :  
  
-   zéro \(0\) pour indiquer que l'heure d'hiver est active ;  
  
-   une valeur supérieure à 0 pour indiquer que l'heure d'été est active ;  
  
-   une valeur inférieure à zéro pour que le code de la bibliothèque Runtime C calcule si l'heure active est l'heure d'hiver ou l'heure d'été.  
  
 La bibliothèque Runtime C utilise la variable d’environnement TZ pour déterminer l’heure correcte. Si TZ n’est pas définie, le système d’exploitation est interrogé pour obtenir l’heure correcte régionaux comportement au moment.`tm_isdst` est un champ obligatoire. S’il est ne pas définie, sa valeur est indéfinie et la valeur de retour de `mktime` est imprévisible.  
  
 La plage de la `_mkgmtime32` sert à partir du 1er janvier 1970 à minuit UTC à 23:59:59 18 janvier 2038, UTC. La plage de `_mkgmtime64` se situe entre le 1er janvier 1970 à minuit UTC et 23:59:59 le 31 décembre 3000, UTC. Une valeur de retour de \-1 entraîne une date hors limites. La plage de `_mkgmtime` varie selon que `_USE_32BIT_TIME_T` est défini. Si non défini \(la valeur par défaut\) la plage est de `_mkgmtime64`; Sinon, la plage est limitée à la plage de 32 bits de `_mkgmtime32`.  
  
 Notez que `gmtime` et `localtime` utilisent une seule mémoire tampon allouée de manière statique pour la conversion. Si vous fournissez cette mémoire tampon à `mkgmtime`, le contenu précédent est détruit.  
  
## Exemple  
  
```  
// crt_mkgmtime.c  
#include <stdio.h>  
#include <time.h>  
  
int main()  
{  
    struct tm t1, t2;  
    time_t now, mytime, gmtime;  
    char buff[30];  
  
    time( & now );  
  
    _localtime64_s( &t1, &now );  
    _gmtime64_s( &t2, &now );  
  
    mytime = mktime(&t1);  
    gmtime = _mkgmtime(&t2);  
  
    printf("Seconds since midnight, January 1, 1970\n");  
    printf("My time: %I64d\nGM time (UTC): %I64d\n\n", mytime, gmtime);  
  
    /* Use asctime_s to display these times. */  
  
    _localtime64_s( &t1, &mytime );  
    asctime_s( buff, sizeof(buff), &t1 );  
    printf( "Local Time: %s\n", buff );  
  
    _gmtime64_s( &t2, &gmtime );  
    asctime_s( buff, sizeof(buff), &t2 );  
    printf( "Greenwich Mean Time: %s\n", buff );  
  
}  
```  
  
## Résultat de l'exemple  
  
```  
Seconds since midnight, January 1, 1970  
My time: 1171588492  
GM time (UTC): 1171588492  
  
Local Time: Thu Feb 15 17:14:52 2007  
  
Greenwich Mean Time: Fri Feb 16 01:14:52 2007  
```  
  
 L’exemple suivant montre comment la structure incomplet est remplie avec les valeurs calculées de la journée de la semaine et le jour de l’année.  
  
```  
// crt_mkgmtime2.c  
#include <stdio.h>  
#include <time.h>  
#include <memory.h>  
  
int main()  
{  
    struct tm t1, t2;  
    time_t gmtime;  
    char buff[30];  
  
    memset(&t1, 0, sizeof(struct tm));  
    memset(&t2, 0, sizeof(struct tm));  
  
    t1.tm_mon = 1;  
    t1.tm_isdst = 0;  
    t1.tm_year = 103;  
    t1.tm_mday = 12;  
  
    // The day of the week and year will be incorrect in the output here.  
    asctime_s( buff, sizeof(buff), &t1);  
    printf("Before calling _mkgmtime, t1 = %s t.tm_yday = %d\n",  
            buff, t1.tm_yday );  
  
    gmtime = _mkgmtime(&t1);  
  
    // The correct day of the week and year were determined.  
    asctime_s( buff, sizeof(buff), &t1);  
    printf("After calling _mkgmtime, t1 = %s t.tm_yday = %d\n",  
            buff, t1.tm_yday );  
  
}  
```  
  
## Sortie  
  
```  
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003  
 t.tm_yday = 0  
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003  
 t.tm_yday = 42  
```  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)