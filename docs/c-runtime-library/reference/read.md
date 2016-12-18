---
title: "_read | Microsoft Docs"
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
  - "_read"
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
  - "_read"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_read (fonction)"
  - "données (C++), lire"
  - "données (CRT)"
  - "fichiers (C++), lire"
  - "read (fonction)"
  - "lire des données (C++)"
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _read
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Reads data from a file.  
  
## Syntaxe  
  
```  
  
      int _read(  
   int fd,  
   void *buffer,  
   unsigned int count   
);  
```  
  
#### Paramètres  
 `fd`  
 Descripteurs de fichier faisant référence au fichier ouvert.  
  
 *buffer*  
 Emplacement de stockage pour les données.  
  
 *count*  
 Nombre maximal d'octets.  
  
## Valeur de retour  
 \_**read** retourne le nombre d'octets, qui peut s'avérer inférieur à *count* s'il y a moins que *count* octets restant dans le fichier ou si le fichier a été ouvert en mode texte, auquel cas chaque paire carriage return–line feed \(CR\-LF\) est remplacée par un caractère de saut de ligne.  Seul le caractère de saut de ligne est compté dans la valeur de retour.  Le remplacement n'affecte pas le pointeur de fichier.  
  
 Si la fonction tente de lire la fin de fichier, elle retourne 0.  Si `fd` est invalide, le fichier n'est pas ouvert pour la lecture, ou le fichier est verrouillé, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, la fonction retourne \-1 et `errno` en `EBADF`.  
  
 Si *buffer* est **NULL**, le gestionnaire de paramètres invalide est appellé.  Si l'execution est autorisée à se poursuivre, la fonction retourne \-1 et `errno` retourne `EINVAL`.  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `_read` lit une valeur maximale de *count* octets dans *buffer* à partir du fichier associé à `fd`.  L'opération de lecture commence à la position actuelle du pointeur de fichier \(le cas échéant\) associé au fichier donné.  Après l'opération de lecture, le pointeur de fichier pointe vers le prochain caractère non lu.  
  
 Si le fichier a été ouvert en mode texte, la lecture se termine lorsque `_read` rencontre un caractère CTRL\+Z, qui est traitée comme indicateur de fin de fichier.  Utiliser [\_lseek](../../c-runtime-library/reference/lseek-lseeki64.md) pour désactiver l'indicateur de fin de fichier.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_read`|\<io.h,\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_read.c  
/* This program opens a file named crt_read.txt  
 * and tries to read 60,000 bytes from  
 * that file using _read. It then displays the  
 * actual number of bytes read.  
 */  
  
#include <fcntl.h>      /* Needed only for _O_RDWR definition */  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <share.h>  
  
char buffer[60000];  
  
int main( void )  
{  
   int fh;  
   unsigned int nbytes = 60000, bytesread;  
  
   /* Open file for input: */  
   if( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ) )  
   {  
      perror( "open failed on input file" );  
      exit( 1 );  
   }  
  
   /* Read in input: */  
   if( ( bytesread = _read( fh, buffer, nbytes ) ) <= 0 )  
      perror( "Problem reading file" );  
   else  
      printf( "Read %u bytes from file\n", bytesread );  
  
   _close( fh );  
}  
```  
  
## Entrée : crt\_read.txt  
  
```  
Line one.  
Line two.  
```  
  
## Sortie  
  
```  
Read 19 bytes from file  
```  
  
## Voir aussi  
 [E\/S niveau bas](../../c-runtime-library/low-level-i-o.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_write](../../c-runtime-library/reference/write.md)