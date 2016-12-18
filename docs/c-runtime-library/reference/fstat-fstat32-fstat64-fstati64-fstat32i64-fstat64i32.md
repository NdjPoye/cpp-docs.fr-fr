---
title: "_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fstat32"
  - "_fstat64"
  - "_fstati64"
  - "_fstat"
  - "_fstat64i32"
  - "_fstat32i64"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_fstat32i64"
  - "fstat"
  - "fstat64i32"
  - "_fstat64"
  - "_fstati64"
  - "fstat64"
  - "_fstat32"
  - "fstat32i64"
  - "fstati64"
  - "_fstat"
  - "fstat32"
  - "_fstat64i32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fstat64 (fonction)"
  - "fstati64 (fonction)"
  - "_fstat64i32 (fonction)"
  - "_fstat32i64 (fonction)"
  - "_fstat32 (fonction)"
  - "informations relatives aux fichiers"
  - "fstat64i32 (fonction)"
  - "fstat32 (fonction)"
  - "fstat (fonction)"
  - "fstat64 (fonction)"
  - "_fstat (fonction)"
  - "_fstati64 (fonction)"
  - "fstat32i64 (fonction)"
ms.assetid: 088f5e7a-9636-4cf7-ab8e-e28d2aa4280a
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient des informations sur un fichier ouvert.  
  
## Syntaxe  
  
```  
int _fstat(   
   int fd,  
   struct _stat *buffer   
);  
int _fstat32(   
   int fd,  
   struct __stat32 *buffer   
);  
int _fstat64(   
   int fd,  
   struct __stat64 *buffer   
);  
int _fstati64(   
   int fd,  
   struct _stati64 *buffer   
);  
int _fstat32i64(   
   int fd,  
   struct _stat32i64 *buffer   
);  
int _fstat64i32(   
   int fd,  
   struct _stat64i32 *buffer   
);  
```  
  
#### Paramètres  
 `fd`  
 Descripteur du fichier ouvert.  
  
 `buffer`  
 Pointeur vers la structure pour stocker les résultats.  
  
## Valeur de retour  
 Retourne 0 si les informations d’état des fichiers sont obtenues. Une valeur de retour égale à –1 indique une erreur. Si le descripteur de fichier n’est pas valide ou `buffer` est `NULL`, le Gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, `errno` a la valeur `EBADF`, dans le cas d’un descripteur de fichier non valide ou à `EINVAL`, Si `buffer` est `NULL`.  
  
## Notes  
 Le `_fstat` fonction obtient des informations sur le fichier ouvert associé `fd` et le stocke dans la structure vers laquelle pointée `buffer`. Le `_stat` structure, définie dans sys\\stat.h, contient les champs suivants.  
  
 `st_atime`  
 Heure du dernier accès de fichier.  
  
 `st_ctime`  
 Heure de la création du fichier.  
  
 `st_dev`  
 Si un périphérique, `fd`; Sinon, 0.  
  
 `st_mode`  
 Masque de bits pour les informations relatives au mode de fichier. Le `_S_IFCHR` bit est défini si `fd` fait référence à un périphérique. Le `_S_IFREG` bit est défini si `fd` fait référence à un fichier ordinaire. Les bits en lecture\/écriture sont définis en fonction du mode d’autorisation du fichier.`_S_IFCHR` et autres constantes sont définies dans sys\\stat.h.  
  
 `st_mtime`  
 Heure de la dernière modification du fichier.  
  
 `st_nlink`  
 Toujours 1 sur les systèmes de fichiers autres que NTFS.  
  
 `st_rdev`  
 Si un périphérique, `fd`; Sinon, 0.  
  
 `st_size`  
 Taille du fichier en octets.  
  
 Si `fd` fait référence à un périphérique, le `st_atime`, `st_ctime`, `st_mtime`, et `st_size` champs ne sont pas significatifs.  
  
 Étant donné que Stat.h utilise le [\_dev\_t](../../c-runtime-library/standard-types.md) type, qui est défini dans Types.h, vous devez inclure Types.h avant Stat.h dans votre code.  
  
 `_fstat64`, qui utilise le `__stat64` structure, autorise les dates de création de fichiers d’exprimer à 23:59:59 le 31 décembre 3000 UTC ; tandis que les autres fonctions représentent uniquement les dates et 23:59:59 18 janvier 2038, UTC. Minuit, le 1er janvier 1970, est la limite inférieure de la plage de dates pour toutes ces fonctions.  
  
 Variantes de ces fonctions prend en charge les types au moment de 32 bits ou 64 bits et les longueurs de fichiers 32 bits ou 64 bits. Le premier suffixe numérique \(`32` ou `64`\) indique la taille du type d’heure utilisé ; le deuxième suffixe est `i32` ou `i64`, qui indique si la taille du fichier est représentée comme un entier 32 bits ou 64 bits.  
  
 `_fstat` est équivalent à `_fstat64i32`, et `struct``_stat` contient une heure de 64 bits. Cela est vrai, sauf si `_USE_32BIT_TIME_T` est défini, auquel cas l’ancien comportement en vigueur, `_fstat` utilise une durée de 32 bits, et `struct``_stat` contient une heure de 32 bits. Cela vaut pour `_fstati64`.  
  
### Variantes de type d’heure et de type de longueur de fichier de \_stat  
  
|Fonctions|\_USE\_32BIT\_TIME\_T défini ?|Type d’heure|Type de longueur de fichier|  
|---------------|------------------------------------|------------------|---------------------------------|  
|`_fstat`|Non défini|64 bits|32 bits|  
|`_fstat`|Défini|32 bits|32 bits|  
|`_fstat32`|Non affecté par la définition de macro|32 bits|32 bits|  
|`_fstat64`|Non affecté par la définition de macro|64 bits|64 bits|  
|`_fstati64`|Non défini|64 bits|64 bits|  
|`_fstati64`|Défini|32 bits|64 bits|  
|`_fstat32i64`|Non affecté par la définition de macro|32 bits|64 bits|  
|`_fstat64i32`|Non affecté par la définition de macro|64 bits|32 bits|  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_fstat`|\< sys\/Stat.h \> et \< sys\/types.h \>|  
|`_fstat32`|\< sys\/Stat.h \> et \< sys\/types.h \>|  
|`_fstat64`|\< sys\/Stat.h \> et \< sys\/types.h \>|  
|`_fstati64`|\< sys\/Stat.h \> et \< sys\/types.h \>|  
|`_fstat32i64`|\< sys\/Stat.h \> et \< sys\/types.h \>|  
|`_fstat64i32`|\< sys\/Stat.h \> et \< sys\/types.h \>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_fstat.c  
// This program uses _fstat to report  
// the size of a file named F_STAT.OUT.  
  
#include <io.h>  
#include <fcntl.h>  
#include <time.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <errno.h>  
#include <share.h>  
  
int main( void )  
{  
   struct _stat buf;  
   int fd, result;  
   char buffer[] = "A line to output";  
   char timebuf[26];  
   errno_t err;  
  
   _sopen_s( &fd,  
             "f_stat.out",  
             _O_CREAT | _O_WRONLY | _O_TRUNC,  
             _SH_DENYNO,  
             _S_IREAD | _S_IWRITE );  
   if( fd != -1 )  
      _write( fd, buffer, strlen( buffer ) );  
  
   // Get data associated with "fd":   
   result = _fstat( fd, &buf );  
  
   // Check if statistics are valid:   
   if( result != 0 )  
   {  
      if (errno == EBADF)  
        printf( "Bad file descriptor.\n" );  
      else if (errno == EINVAL)  
        printf( "Invalid argument to _fstat.\n" );  
   }  
   else  
   {  
      printf( "File size     : %ld\n", buf.st_size );  
      err = ctime_s(timebuf, 26, &buf.st_mtime);  
      if (err)  
      {  
         printf("Invalid argument to ctime_s.");  
         exit(1);  
      }  
      printf( "Time modified : %s", timebuf );  
   }  
   _close( fd );  
}  
```  
  
```Output  
Taille du fichier : modification 16 : mer mai 07 15:25:11 2003  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_filelength, \_filelengthi64](../../c-runtime-library/reference/filelength-filelengthi64.md)   
 [\_stat, \_wstat, fonctions](../../c-runtime-library/reference/stat-functions.md)