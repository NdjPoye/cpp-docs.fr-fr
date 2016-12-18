---
title: "_chsize | Microsoft Docs"
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
  - "_chsize"
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
  - "_chsize"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_chsize (fonction)"
  - "chsize (fonction)"
  - "fichiers (C++), modifier la taille"
  - "taille"
  - "taille, changer de fichier"
ms.assetid: b3e881c5-7b27-4837-a3d4-c51591ab10ff
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _chsize
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Changes the size of a file.  Un version plus sûr de [\_chsize\_s](../../c-runtime-library/reference/chsize-s.md) est disponible ; consultez .  
  
## Syntaxe  
  
```  
int _chsize(   
   int fd,  
   long size   
);  
```  
  
#### Paramètres  
 `fd`  
 Descripteurs de fichier faisant référence au fichier ouvert.  
  
 `size`  
 Longueur du fichier en octets.  
  
## Valeur de retour  
 `_chsize` retourne la valeur 0 si la taille du fichier a été modifiée.  Une valeur de retour de – 1 indique une erreur : `errno` a la valeur `EACCES` si le fichier spécifié est verrouillé contre tout accès, à `EBADF` si le fichier spécifié est en lecture seule ou si l'un descripteur est invalide, à `ENOSPC` si aucun espace ne reste sur le périphérique, ou à `EINVAL` si `size` est inférieure à zéro.  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes de retour.  
  
## Notes  
 La fonction `_chsize` étend ou tronque le fichier associé à `fd` à la longueur spécifiée par `size`.  Le fichier doit être ouvert dans un mode qui permet d'écrire.  Les caractères Null \("\\0 "\) sont ajoutés si le fichier est étendu.  Si le fichier est tronqué, toutes les données de la fin du fichier original raccourci sont perdues.  
  
 Cette fonction valide ses paramètres.  Si `size` est inférieure à zéro ou que`fd` est un mauvais descripteur de fichier, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_chsize`|\<io.h,\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_chsize.c  
// This program uses _filelength to report the size  
// of a file before and after modifying it with _chsize.  
  
#include <io.h>  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <share.h>  
  
int main( void )  
{  
   int fh, result;  
   unsigned int nbytes = BUFSIZ;  
  
   // Open a file   
   if( _sopen_s( &fh, "data", _O_RDWR | _O_CREAT, _SH_DENYNO,  
                 _S_IREAD | _S_IWRITE ) == 0 )  
   {  
      printf( "File length before: %ld\n", _filelength( fh ) );  
      if( ( result = _chsize( fh, 329678 ) ) == 0 )  
         printf( "Size successfully changed\n" );  
      else  
         printf( "Problem in changing the size\n" );  
      printf( "File length after:  %ld\n", _filelength( fh ) );  
      _close( fh );  
   }  
}  
```  
  
  **Longueur de fichier jusque là : 0**  
**Taille correctement modifiée**  
**Longueur de fichier après :  329678**   
## Équivalent .NET Framework  
  
-   [System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx)  
  
-   [System::IO::FileStream::FileStream](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_sopen, \_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)