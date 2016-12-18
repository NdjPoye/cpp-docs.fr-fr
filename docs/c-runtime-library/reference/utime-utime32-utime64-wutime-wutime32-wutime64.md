---
title: "_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_utime64"
  - "_utime"
  - "_wutime"
  - "_wutime64"
  - "_wutime32"
  - "_utime32"
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
  - "_tutime"
  - "_utime64"
  - "wutime"
  - "utime32"
  - "wutime64"
  - "_utime"
  - "wutime32"
  - "_wutime"
  - "utime"
  - "utime64"
  - "_wutime64"
  - "_utime32"
  - "_tutime64"
  - "_wutime32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tutime, fonction"
  - "utime32, fonction"
  - "utime64, fonction"
  - "_utime, fonction"
  - "_tutime32, fonction"
  - "date/heure [C++], modification des fichiers"
  - "wutime, fonction"
  - "_wutime, fonction"
  - "_wutime32, fonction"
  - "_tutime64, fonction"
  - "_tutime, fonction"
  - "fichiers [C++], date/heure de modification"
  - "_wutime64, fonction"
  - "_utime32, fonction"
  - "utime, fonction"
  - "_utime64, fonction"
  - "wutime64, fonction"
  - "wutime32, fonction"
  - "tutime64, fonction"
  - "tutime32, fonction"
ms.assetid: 8d482d40-19b9-4591-bfee-5d7f601d1a9e
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _utime, _utime32, _utime64, _wutime, _wutime32, _wutime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définir l’heure de modification de fichier.  
  
## Syntaxe  
  
```  
int _utime(  
   const char *filename,  
   struct _utimbuf *times   
);  
int _utime32(  
   const char *filename,  
   struct __utimbuf32 *times   
);  
int _utime64(  
   const char *filename,  
   struct __utimbuf64 *times   
);  
int _wutime(  
   const wchar_t *filename,  
   struct _utimbuf *times   
);  
int _wutime32(  
   const wchar_t *filename,  
   struct __utimbuf32 *times   
);  
int _wutime64(  
   const wchar_t *filename,  
   struct __utimbuf64 *times   
);  
```  
  
#### Paramètres  
 `filename`  
 Pointeur vers une chaîne qui contient le chemin d’accès ou le nom de fichier.  
  
 `times`  
 Pointeur vers les valeurs stockées.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne 0 si l’heure de modification de fichier a été modifié. Une valeur de retour égale à –1 indique une erreur. Si un paramètre non valide est passé, le Gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, ces fonctions retournent \-1 et `errno` est défini sur l’une des valeurs suivantes :  
  
 `EACCES`  
 Chemin d’accès spécifie le répertoire ou le fichier en lecture seule  
  
 `EINVAL`  
 Non valide `times` argument  
  
 `EMFILE`  
 Trop de fichiers ouverts \(le fichier doit être ouvert pour modifier son heure de modification\)  
  
 `ENOENT`  
 Chemin d’accès ou nom de fichier introuvable  
  
 Consultez la page [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d’informations sur les autres codes de retour.  
  
 La date peut être modifiée pour un fichier si la date de modification est après le 1er janvier 1970 à minuit et avant la date de fin de la fonction utilisée.`_utime` et `_wutime` utilisent une valeur d’heure de 64 bits, la date de fin est 23:59:59 le 31 décembre 3000, UTC. Si `_USE_32BIT_TIME_T` est définie pour forcer l’ancien comportement, la date de fin est 23:59:59 18 janvier 2038, UTC.`_utime32` ou `_wutime32` utiliser un type 32 bits temps indépendamment de si `_USE_32BIT_TIME_T` est défini, et ont toujours la date de fin antérieure.`_utime64` ou `_wutime64` utilisent toujours le type au moment de 64 bits, ces fonctions toujours prendre en charge que la date de fin ultérieure.  
  
## Notes  
 Le `_utime` fonction définit l’heure de modification pour le fichier spécifié par `filename`*.* Pour modifier l’heure, le processus doit avoir un accès en écriture au fichier. Dans le système d’exploitation Windows, vous pouvez modifier le temps d’accès et l’heure de modification dans le `_utimbuf` structure. Si `times` est un `NULL` pointeur, l’heure de modification est définie à l’heure locale actuelle. Dans le cas contraire, `times` doit pointer vers une structure de type `_utimbuf`, défini dans SYS\\UTIME. H.  
  
 Le `_utimbuf` structure stocke les heures d’accès et de modification de fichier utilisés par `_utime` pour modifier les dates de modification de fichier. La structure a les champs suivants, qui sont tous deux de type `time_t`:  
  
 `actime`  
 Temps d’accès au fichier  
  
 `modtime`  
 Heure de modification de fichier  
  
 Des versions spécifiques de le `_utimbuf` structure \(`_utimebuf32` et `__utimbuf64`\) sont définies en utilisant les versions 32 bits et 64 bits de type heure. Ils sont utilisés dans les versions 32 bits et 64 bits spécifiques de cette fonction.`_utimbuf` par défaut utilise lui\-même un type au moment de 64 bits, sauf si `_USE_32BIT_TIME_T` est défini.  
  
 `_utime` est identique à `_futime` sauf que le `filename` argument de `_utime` est un nom de fichier ou un chemin d’accès à un fichier, plutôt qu’un descripteur de fichier d’un fichier ouvert.  
  
 `_wutime` est une version à caractères larges de `_utime` ; l'argument `filename` de `_wutime` est une chaîne à caractères larges. Ces fonctions se comportent sinon de façon identique.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tutime`|`_utime`|`_utime`|`_wutime`|  
|`_tutime32`|`_utime32`|`_utime32`|`_wutime32`|  
|`_tutime64`|`_utime64`|`_utime64`|`_wutime64`|  
  
## Configuration requise  
  
|Routine|En\-têtes requis|En\-têtes facultatifs|  
|-------------|----------------------|---------------------------|  
|`_utime`, `_utime32`, `_utime64`|\< sys\/utime.h \>|\<errno.h\>|  
|`_utime64`|\< sys\/utime.h \>|\<errno.h\>|  
|`_wutime`|\< utime.h \> ou \< wchar.h \>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Ce programme utilise `_utime` pour définir l’heure de modification de fichier à l’heure actuelle.  
  
```  
// crt_utime.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <sys/types.h>  
#include <sys/utime.h>  
#include <time.h>  
  
int main( void )  
{  
   struct tm tma = {0}, tmm = {0};  
   struct _utimbuf ut;  
  
   // Fill out the accessed time structure  
   tma.tm_hour = 12;  
   tma.tm_isdst = 0;  
   tma.tm_mday = 15;  
   tma.tm_min = 0;  
   tma.tm_mon = 0;  
   tma.tm_sec = 0;  
   tma.tm_year = 103;  
  
   // Fill out the modified time structure  
   tmm.tm_hour = 12;  
   tmm.tm_isdst = 0;  
   tmm.tm_mday = 15;  
   tmm.tm_min = 0;  
   tmm.tm_mon = 0;  
   tmm.tm_sec = 0;  
   tmm.tm_year = 102;  
  
   // Convert tm to time_t  
   ut.actime = mktime(&tma);  
   ut.modtime = mktime(&tmm);  
  
   // Show file time before and after  
   system( "dir crt_utime.c" );  
   if( _utime( "crt_utime.c", &ut ) == -1 )  
      perror( "_utime failed\n" );  
   else  
      printf( "File time modified\n" );  
   system( "dir crt_utime.c" );  
}  
```  
  
## Résultat de l'exemple  
  
```  
Volume in drive C has no label.  
 Volume Serial Number is 9CAC-DE74  
  
 Directory of C:\test  
  
01/09/2003  05:38 PM               935 crt_utime.c  
               1 File(s)            935 bytes  
               0 Dir(s)  20,742,955,008 bytes free  
File time modified  
 Volume in drive C has no label.  
 Volume Serial Number is 9CAC-DE74  
  
 Directory of C:\test  
  
01/15/2002  12:00 PM               935 crt_utime.c  
               1 File(s)            935 bytes  
               0 Dir(s)  20,742,955,008 bytes free  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [\_futime, \_futime32, \_futime64](../../c-runtime-library/reference/futime-futime32-futime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [\_stat, \_wstat, fonctions](../../c-runtime-library/reference/stat-functions.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)