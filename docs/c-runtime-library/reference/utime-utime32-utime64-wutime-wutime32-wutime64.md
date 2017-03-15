---
title: _utime, _utime32, _utime64, _wutime, _wutime32, _wutime64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _utime64
- _utime
- _wutime
- _wutime64
- _wutime32
- _utime32
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tutime
- _utime64
- wutime
- utime32
- wutime64
- _utime
- wutime32
- _wutime
- utime
- utime64
- _wutime64
- _utime32
- _tutime64
- _wutime32
dev_langs:
- C++
helpviewer_keywords:
- tutime function
- utime32 function
- utime64 function
- _utime function
- _tutime32 function
- time [C++], file modification
- wutime function
- _wutime function
- _wutime32 function
- _tutime64 function
- _tutime function
- files [C++], modification time
- _wutime64 function
- _utime32 function
- utime function
- _utime64 function
- wutime64 function
- wutime32 function
- tutime64 function
- tutime32 function
ms.assetid: 8d482d40-19b9-4591-bfee-5d7f601d1a9e
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 7d8823bfe5650634d3fb079d2910e98409622ec6
ms.lasthandoff: 02/24/2017

---
# <a name="utime-utime32-utime64-wutime-wutime32-wutime64"></a>_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64
Définissent l’heure de modification des fichiers.  
  
## <a name="syntax"></a>Syntaxe  
  
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
  
#### <a name="parameters"></a>Paramètres  
 `filename`  
 Pointeur désignant une chaîne qui contient le chemin ou le nom de fichier.  
  
 `times`  
 Pointeur désignant les valeurs d’heure stockées.  
  
## <a name="return-value"></a>Valeur de retour  
 Chacune de ces fonctions retourne 0 si l’heure de modification de fichier a changé. Une valeur de retour égale à –1 indique une erreur. Si un paramètre non valide est transmis, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, ces fonctions retournent -1 et `errno` prend l’une des valeurs suivantes :  
  
 `EACCES`  
 Le chemin indique le répertoire ou un fichier en lecture seule.  
  
 `EINVAL`  
 Argument `times` non valide.  
  
 `EMFILE`  
 Trop de fichiers ouverts (le fichier doit être ouvert pour modifier son heure de modification).  
  
 `ENOENT`  
 Chemin ou nom de fichier introuvable.  
  
 Pour plus d’informations sur ces codes de retour et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 La date d’un fichier peut être modifiée si la date de modification est postérieure au 1er janvier 1970 à minuit et antérieure à la date de fin de la fonction utilisée. `_utime` et `_wutime` utilisent une valeur d’heure de 64 bits, de sorte que la date de fin est le 31 décembre 3000, UTC à 23:59:59. Si `_USE_32BIT_TIME_T` est définie pour imposer l’ancien comportement, la date de fin est le 18 janvier 2038, UTC à 23:59:59. `_utime32` ou `_wutime32` utilisent un type d’heure de 32 bits, que la fonction `_USE_32BIT_TIME_T` soit ou non définie, et ont toujours la date de fin la plus ancienne. `_utime64` ou `_wutime64` utilisent toujours le type d’heure de 64 bits, si bien que ces fonctions prennent toujours en charge la date de fin la plus lointaine.  
  
## <a name="remarks"></a>Notes  
 La fonction `_utime` définit l’heure de modification du fichier spécifié par `filename`*.* Pour que la modification de l’heure soit possible, le processus doit avoir un accès en écriture au fichier. Dans le système d’exploitation Windows, vous pouvez modifier l’heure d’accès et l’heure de modification dans la structure `_utimbuf`. Si `times` est un pointeur `NULL`, l’heure de modification correspond à l’heure locale du moment. Dans le cas contraire, `times` doit pointer vers une structure de type `_utimbuf`, définie dans SYS\UTIME.H.  
  
 La structure `_utimbuf` stocke les heures d’accès et de modification de fichier utilisées par `_utime` pour changer les dates de modification de fichier. La structure contient les champs suivants, qui sont tous deux de type `time_t` :  
  
 `actime`  
 Heure d’accès au fichier.  
  
 `modtime`  
 Heure de modification du fichier.  
  
 Des versions spécifiques de la structure `_utimbuf` (`_utimebuf32` et `__utimbuf64`) sont définies avec les versions 32 bits et 64 bits du type d’heure. Elles sont utilisées dans les versions spécifiques 32 bits et 64 bits de cette fonction. La structure `_utimbuf` proprement dite utilise par défaut un type d’heure de 64 bits, à moins que `_USE_32BIT_TIME_T` soit défini.  
  
 `_utime` est identique à `_futime`, sauf que l’argument `filename` de `_utime` est un nom de fichier ou un chemin de fichier, et non un descripteur de fichier ouvert.  
  
 `_wutime` est une version à caractères larges de `_utime` ; l'argument `filename` de `_wutime` est une chaîne à caractères larges. Ces fonctions se comportent sinon de façon identique.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tutime`|`_utime`|`_utime`|`_wutime`|  
|`_tutime32`|`_utime32`|`_utime32`|`_wutime32`|  
|`_tutime64`|`_utime64`|`_utime64`|`_wutime64`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-têtes obligatoires|En-têtes facultatifs|  
|-------------|----------------------|----------------------|  
|`_utime`, `_utime32`, `_utime64`|\<sys/utime.h>|\<errno.h>|  
|`_utime64`|\<sys/utime.h>|\<errno.h>|  
|`_wutime`|\<utime.h> ou \<wchar.h>|\<errno.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Ce programme utilise `_utime` pour fixer l’heure de modification de fichier à l’heure du moment.  
  
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
  
## <a name="sample-output"></a>Résultat de l'exemple  
  
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
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [_futime, _futime32, _futime64](../../c-runtime-library/reference/futime-futime32-futime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [_stat, _wstat, fonctions](../../c-runtime-library/reference/stat-functions.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
