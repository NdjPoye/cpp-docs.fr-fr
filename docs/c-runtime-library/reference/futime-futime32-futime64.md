---
title: "_futime, _futime32, _futime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_futime64"
  - "_futime32"
  - "_futime"
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
  - "futime"
  - "_futime"
  - "futime64"
  - "_futime64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_futime (fonction)"
  - "futime32 (fonction)"
  - "futime64 (fonction)"
  - "heure de modification de fichier (C++)"
  - "_futime64 (fonction)"
  - "futime (fonction)"
  - "_futime32 (fonction)"
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _futime, _futime32, _futime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sets the modification time on an open file.  
  
## Syntaxe  
  
```  
int _futime(   
   int fd,  
   struct _utimbuf *filetime   
);  
int _futime32(   
   int fd,  
   struct __utimbuf32 *filetime   
);  
int _futime64(   
   int fd,  
   struct __utimbuf64 *filetime   
);  
```  
  
#### Paramètres  
 `fd`  
 Descripteur de fichier du fichier ouvert.  
  
 `filetime`  
 Pointeur vers la structure contenant la nouvelle date de modification.  
  
## Valeur de retour  
 En cas de réussite, retourne .  Si une erreur advient, le gestionnaire de paramètres invalides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'execution est autorisée à continuer, la fonction retourne – 1 et `errno` prend la valeur `EBADF`, indiquant un descripteur de fichier invalide, ou `EINVAL`, indiquant qu'un paramètre est non valide.  
  
## Notes  
 La routine `_futime` définit la date de modification et l'heure de l'accès sur le fichier ouvert associé à `fd`*.* `_futime` est identique à [\_utime](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md), sauf que son argument est un descripteur de fichier d'un fichier ouvert, au lieu du nom d'un fichier ou d'un chemin d'accès d'un fichier.  La structure `_utimbuf` contient des champs pour la nouvelle date et heure de modification.  Les deux champs doivent contenir des valeurs valides.  `_utimbuf32` et `_utimbuf64` sont identiques à `_utimbuf`, sauf en ce qui concerne l'utilisation de types temps 32 et 64 bits respectivement.  `_futime` et `_utimbuf` utilisent un type temps 64 bits et `_futime` est identique dans son comportement à `_futime64`.  Si vous devez forcer le comportement antérieur, définissez `_USE_32BIT_TIME_T`.  Faire ceci, force `_futime` à etre identique en comportement à `_futime32` et fait en sorte que la structure `_utimbuf` utilises le type d'heure 32 bits, ce qui équivaut à `__utimbuf32`.  
  
 `_futime64`, qui utilise la structure `__utimbuf64`, peut lire et modifier les dates de fichier par 23h59 : 59, le 31 décembre, 3000, en valeurs UTC ; alors qu'un appel à `_futime32` échoue si la date du fichier est ultérieure à 19h14 : Le 7 janvier 18, 2038, en valeurs UTC.  Minuit, le 1er janvier 1970, est la limite inférieure de la plage de dates pour ces deux fonctions.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|En\-tête facultatif|  
|--------------|---------------------|-------------------------|  
|`_futime`|\<système\/utime.h\>|\<errno.h\>|  
|`_futime32`|\<système\/utime.h\>|\<errno.h\>|  
|`_futime64`|\<système\/utime.h\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_futime.c  
// This program uses _futime to set the  
// file-modification time to the current time.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <fcntl.h>  
#include <io.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <sys/utime.h>  
#include <share.h>  
  
int main( void )  
{  
   int hFile;  
  
   // Show file time before and after.   
   system( "dir crt_futime.c_input" );  
  
   _sopen_s( &hFile, "crt_futime.c_input", _O_RDWR, _SH_DENYNO, 0 );  
  
   if( _futime( hFile, NULL ) == -1 )  
      perror( "_futime failed\n" );  
   else  
      printf( "File time modified\n" );  
  
   _close (hFile);  
  
   system( "dir crt_futime.c_input" );  
}  
```  
  
## Entrée : crt\_futime.c\_input  
  
```  
Arbitrary file contents.  
```  
  
### Résultat de l'exemple  
  
```  
Volume in drive Z has no label.  
 Volume Serial Number is 5C68-57C1  
  
 Directory of Z:\crt  
  
03/25/2004  10:40 AM                24 crt_futime.c_input  
               1 File(s)             24 bytes  
               0 Dir(s)  24,268,476,416 bytes free  
 Volume in drive Z has no label.  
 Volume Serial Number is 5C68-57C1  
  
 Directory of Z:\crt  
  
03/25/2004  10:41 AM                24 crt_futime.c_input  
               1 File(s)             24 bytes  
               0 Dir(s)  24,268,476,416 bytes free  
File time modified  
```  
  
## Équivalent .NET Framework  
  
-   [System.IO.File::GetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastaccesstime.aspx)  
  
-   [System.IO.File::GetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastwritetime.aspx)  
  
-   [System.IO.File::GetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.setcreationtime.aspx)  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)