---
title: _lseek, _lseeki64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _lseeki64
- _lseek
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _lseeki64
- _lseek
- lseeki64
dev_langs:
- C++
helpviewer_keywords:
- lseek function
- _lseek function
- _lseeki64 function
- lseeki64 function
- file pointers [C++], moving
- seek file pointers
ms.assetid: aba8a768-d40e-48c3-b38e-473dbd782f93
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: e8e40f4995f17314d70990a84c23c676d31a45d5
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="lseek-lseeki64"></a>_lseek, _lseeki64
Déplace un pointeur de fichier vers l’emplacement spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
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
  
#### <a name="parameters"></a>Paramètres  
 `fd`  
 Descripteur de fichier qui fait référence à un fichier ouvert.  
  
 *offset*  
 Nombre d’octets à partir d’*origin*.  
  
 *origin*  
 Position initiale.  
  
## <a name="return-value"></a>Valeur de retour  
 `_lseek` retourne l’offset, en octets, de la nouvelle position à partir du début du fichier. `_lseeki64` retourne l’offset dans un entier 64 bits. La fonction retourne-1 L pour indiquer une erreur. Si un paramètre non valide est passé, tel qu’un descripteur de fichier incorrect, que la valeur d’*origin* n’est pas valide ou que la position spécifiée par *offset* se situe avant le début du fichier, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, ces fonctions affectent à `errno` la valeur `EBADF` et retournent -1L. Sur les appareils sans fonctionnalités de recherche (tels que les terminaux et les imprimantes), la valeur de retour n’est pas définie.  
  
 Pour plus d’informations sur ces codes d’erreur et autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `_lseek` déplace le pointeur de fichier associé à `fd` vers un nouvel emplacement situé à *offset* octets d’*origin*. L’opération suivante sur le fichier se produit au nouvel emplacement. L’argument *origin* doit être une des constantes suivantes, qui sont définies dans Stdio.h.  
  
 `SEEK_SET`  
 Début du fichier.  
  
 `SEEK_CUR`  
 Position actuelle du pointeur de fichier.  
  
 `SEEK_END`  
 Fin du fichier.  
  
 Vous pouvez utiliser `_lseek` pour repositionner le pointeur n’importe où dans un fichier ou au-delà de la fin du fichier.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_lseek`|\<io.h>|  
|`_lseeki64`|\<io.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
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
  
## <a name="input-crtlseekcinput"></a>Entrée : crt_lseek.c_input  
  
```  
Line one.  
Line two.  
Line three.  
Line four.  
Line five.  
```  
  
## <a name="output"></a>Sortie  
  
```  
Position for beginning of file seek = 0  
Position for current position seek = 10  
Position for end of file seek = 57  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de bas niveau](../../c-runtime-library/low-level-i-o.md)   
 [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [_tell, _telli64](../../c-runtime-library/reference/tell-telli64.md)
