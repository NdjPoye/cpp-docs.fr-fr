---
title: "_strtime, _wstrtime | Microsoft Docs"
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
  - "_wstrtime"
  - "_strtime"
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
  - "_wstrtime"
  - "_strtime"
  - "wstrtime"
  - "strtime"
  - "_tstrtime"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strtime (fonction)"
  - "_tstrtime (fonction)"
  - "_wstrtime (fonction)"
  - "copier des heures dans les mémoires tampons"
  - "strtime (fonction)"
  - "heure, copier"
  - "tstrtime (fonction)"
  - "wstrtime (fonction)"
ms.assetid: 9e538161-cf49-44ec-bca5-c0ab0b9e4ca3
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strtime, _wstrtime
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Copiez l'heure vers une mémoire tampon.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_strtime\_s, \_wstrtime\_s](../../c-runtime-library/reference/strtime-s-wstrtime-s.md).  
  
## Syntaxe  
  
```  
char *_strtime(  
   char *timestr   
);  
wchar_t *_wstrtime(  
   wchar_t *timestr   
);  
template <size_t size>  
char *_strtime(  
   char (&timestr)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wstrtime(  
   wchar_t (&timestr)[size]  
); // C++ only  
```  
  
#### Paramètres  
 `timestr`  
 chaîne heure  
  
## Valeur de retour  
 Retourne un pointeur vers la chaîne de caractère modifiée `timestr`.  
  
## Notes  
 La fonction `_strtime` copie l'heure locale actuelle dans la mémoire tampon désignée par `timestr`*.* L'heure est mise sous la forme `hh:mm:ss` où `hh` sont deux chiffres qui représentent l'heure dans la notation horaire sur 24 heures, `mm` sont deux chiffres qui représentent les minutes après l'heure, et `ss` sont deux chiffres représentant les secondes.  Par exemple, la chaîne `18:23:44` représente 23 minutes et 44 secondes après 18h La mémoire tampon doit etre longue d'au moins 9 octets.  
  
 `_wstrtime` est une version caractères larges de `_strtime`; l'argument et la valeur de retour de `_wstrtime` sont des chaînes de caractères larges.  Ces fonctions se comportent de la même manière dans le cas contraire. Si `timestr` est un pointeur `NULL` ou si `timestr` est mis en forme de manière incorrecte, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exception est autorisée à continuer, ces fonctions retournent NULL et définissent `errno` à `EINVAL` si `timestr` est NULL ou définissent `errno` à `ERANGE` si `timestr` est mis en forme incorrectement.  
  
 En C\+\+, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tstrtime`|`_strtime`|`_strtime`|`_wstrtime`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_strtime`|\<time.h\>|  
|`_wstrtime`|\<time.h\> or \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_strtime.c  
// compile with: /W3  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char tbuffer [9];  
   _strtime( tbuffer ); // C4996  
   // Note: _strtime is deprecated; consider using _strtime_s instead  
   printf( "The current time is %s \n", tbuffer );  
}  
```  
  
  **L'heure actuelle est 14:21:44**   
## Équivalent .NET Framework  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)