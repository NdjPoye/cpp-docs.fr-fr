---
title: "_tell, _telli64 | Microsoft Docs"
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
  - "_telli64"
  - "_tell"
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
  - "tell"
  - "telli64"
  - "_telli64"
  - "_tell"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tell (fonction)"
  - "_telli64 (fonction)"
  - "pointeurs de fichier (C++)"
  - "pointeurs de fichier (C++), obtenir"
  - "tell (fonction)"
  - "telli64 (fonction)"
ms.assetid: 1500e8f9-8fec-4253-9eec-ec66125dfc9b
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _tell, _telli64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient la position du pointeur de fichier.  
  
## Syntaxe  
  
```  
long _tell(  
   int handle  
);  
__int64 _telli64(  
   int handle   
);  
```  
  
#### Paramètres  
 `handle`  
 Descripteurs de fichier faisant référence au fichier ouvert.  
  
## Valeur de retour  
 Position actuelle du pointeur de fichier.  Sur des périphériques incapables d'effectuer des recherches, la valeur de retour n'est pas définie.  
  
 Une valeur de retour de \-1L indique une erreur.  Si `handle` est un descripteur de fichier invalide, le hgestionnaire de paramètre invalide est invoqué, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` à `EBADF` et retournent \-1L.  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ceci et d'autres codes de retour.  
  
## Notes  
 La fonction `_tell` obtient la position actuelle du pointeur de fichier \(le cas échéant\) associé à l'argument `handle`.  La position est exprimée comme le nombre d'octets entre le début du fichier.  De la fonction `_telli64`, cette valeur est exprimée en tant qu'entier 64 bits.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_tell`, `_telli64`|\<io.h,\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_tell.c  
// This program uses _tell to tell the  
// file pointer position after a file read.  
//  
  
#include <io.h>  
#include <stdio.h>  
#include <fcntl.h>  
#include <share.h>  
#include <string.h>  
  
int main( void )  
{  
   int  fh;  
   char buffer[500];  
  
   if ( _sopen_s( &fh, "crt_tell.txt", _O_RDONLY, _SH_DENYNO, 0) )  
   {  
      char buff[50];  
      _strerror_s( buff, sizeof(buff), NULL );  
      printf( buff );  
      exit( -1 );  
   }  
  
   if( _read( fh, buffer, 500 ) > 0 )  
      printf( "Current file position is: %d\n", _tell( fh ) );  
   _close( fh );  
}  
```  
  
## Entrée : crt\_tell.txt  
  
```  
Line one.  
Line two.  
```  
  
### Sortie  
  
```  
Current file position is: 20  
```  
  
## Voir aussi  
 [E\/S niveau bas](../../c-runtime-library/low-level-i-o.md)   
 [ftell, \_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [\_lseek, \_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)