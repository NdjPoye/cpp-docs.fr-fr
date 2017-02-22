---
title: "_lseek, _lseeki64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lseeki64"
  - "_lseek"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_lseeki64"
  - "_lseek"
  - "lseeki64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_lseek (fonction)"
  - "_lseeki64 (fonction)"
  - "pointeurs de fichier (C++), déplacer"
  - "lseek (fonction)"
  - "lseeki64 (fonction)"
  - "rechercher des pointeurs de fichier"
ms.assetid: aba8a768-d40e-48c3-b38e-473dbd782f93
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _lseek, _lseeki64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Déplace le pointeur de fichier vers l'emplacement spécifié.  
  
## Syntaxe  
  
```  
  
      long _lseek(  
   int fd,  
   long offset,  
   int origin   
);  
__int64 _lseeki64(  
   int fd,  
   __int64 offset,  
   int origin   
);  
```  
  
#### Paramètres  
 `fd`  
 Descripteurs de fichier faisant référence au fichier ouvert.  
  
 *offset*  
 Nombre d'octets depuis *origine*.  
  
 *origin*  
 Position initiale.  
  
## Valeur de retour  
 `_lseek` retourne le décalage, en octets, de la nouvelle position depuis le début du fichier.  `_lseeki64` retourne le décalage d'un entier 64 bits.  La fonction retourne – 1L pour indiquer une erreur.  Si on lui transmet un paramètre non valide, tel qu'un mauvais descripteur de fichier, ou si la valeur pour *origine* n'est pas valide ou si une position spécifiée par *le décalage* est antérieure au début du fichier, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` à `EBADF` et retournent \-1L.  Sur des périphériques incapables de rechercher \(tels que les terminaux et les imprimantes\), la valeur de retour n'est pas définie.  
  
 Pour plus d'informations sur ces codes d'erreur et d'autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `_lseek` déplace le pointeur de fichier associé à `fd` vers un nouvel emplacement qui est des octets *offset* depuis *origin*.  L'opération suivante sur le fichier se produit au nouvel emplacement.  L'argument *origine* doit être l'une des constantes suivantes, qui sont définies dans Stdio.h.  
  
 `SEEK_SET`  
 Début du fichier.  
  
 `SEEK_CUR`  
 Position actuelle du pointeur de fichier.  
  
 `SEEK_END`  
 Fin du fichier.  
  
 Vous pouvez utiliser `_lseek` pour repositionner le pointeur n'importe où dans un fichier ou au delà de la fin du fichier.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_lseek`|\<io.h,\>|  
|`_lseeki64`|\<io.h,\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_lseek.c  
/* This program first opens a file named lseek.txt.  
 * It then uses _lseek to find the beginning of the file,  
 * to find the current position in the file, and to find  
 * the end of the file.  
 */  
  
#include <io.h>  
#include <fcntl.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <share.h>  
  
int main( void )  
{  
   int fh;  
   long pos;               /* Position of file pointer */  
   char buffer[10];  
  
   _sopen_s( &fh, "crt_lseek.c_input", _O_RDONLY, _SH_DENYNO, 0 );  
  
   /* Seek the beginning of the file: */  
   pos = _lseek( fh, 0L, SEEK_SET );  
   if( pos == -1L )  
      perror( "_lseek to beginning failed" );  
   else  
      printf( "Position for beginning of file seek = %ld\n", pos );  
  
   /* Move file pointer a little */  
    _read( fh, buffer, 10 );  
  
   /* Find current position: */  
   pos = _lseek( fh, 0L, SEEK_CUR );  
   if( pos == -1L )  
      perror( "_lseek to current position failed" );  
   else  
      printf( "Position for current position seek = %ld\n", pos );  
  
   /* Set the end of the file: */  
   pos = _lseek( fh, 0L, SEEK_END );  
   if( pos == -1L )  
      perror( "_lseek to end failed" );  
   else  
      printf( "Position for end of file seek = %ld\n", pos );  
  
   _close( fh );  
}  
```  
  
## Entrée : crt\_lseek.c\_input  
  
```  
Line one.  
Line two.  
Line three.  
Line four.  
Line five.  
```  
  
## Sortie  
  
```  
Position for beginning of file seek = 0  
Position for current position seek = 10  
Position for end of file seek = 57  
```  
  
## Voir aussi  
 [E\/S niveau bas](../../c-runtime-library/low-level-i-o.md)   
 [fseek, \_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_tell, \_telli64](../../c-runtime-library/reference/tell-telli64.md)