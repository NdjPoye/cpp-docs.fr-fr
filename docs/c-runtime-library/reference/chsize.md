---
title: _chsize | Microsoft Docs
ms.custom: ''
ms.date: 03/29/2018
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _chsize
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
- _chsize
dev_langs:
- C++
helpviewer_keywords:
- size
- _chsize function
- size, changing file
- files [C++], changing size
- chsize function
ms.assetid: b3e881c5-7b27-4837-a3d4-c51591ab10ff
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cec2d058b356cbb7624ee6dd0bbecdfb55c64813
ms.sourcegitcommit: cdd4808dcb274bbb29618286df4d1d4acd35b9bc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2018
---
# <a name="chsize"></a>_chsize

Modifie la taille d’un fichier. Une version plus sécurisée est disponible. Consultez [_chsize_s](../../c-runtime-library/reference/chsize-s.md).

## <a name="syntax"></a>Syntaxe

```C
int _chsize(
   int fd,
   long size
);
```

### <a name="parameters"></a>Paramètres
*fd*<br/>
Descripteur de fichier qui fait référence à un fichier ouvert.

*size*<br/>
Nouvelle longueur, en octets, du fichier.

## <a name="return-value"></a>Valeur de retour

_chsize` returns the value 0 if the file size is successfully changed. A return value of -1 indicates an error: `errno` is set to `EACCES` if the specified file is read-only or the specified file is locked against access, to `EBADF` if the descriptor is invalid, `ENOSPC` if no space is left on the device, or `EINVAL` if `taille » est inférieur à zéro.

Pour plus d’informations sur ces codes de retour et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Notes

La fonction `_chsize` étend ou tronque le fichier associé à `fd` à la longueur spécifiée par `size`. Le fichier doit être ouvert dans un mode qui permet l’écriture. Des caractères Null (« \0 ») sont ajoutés si le fichier est étendu. Si le fichier est tronqué, toutes les données depuis la fin du fichier raccourci jusqu’à la longueur d’origine du fichier sont perdues.

Cette fonction valide ses paramètres. Si `size` est inférieur à zéro ou que `fd` est un descripteur de fichier incorrect, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|En-tête facultatif|
|-------------|---------------------|---------------------|
|`_chsize`|\<io.h>|\<errno.h>|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemple

```C
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

```Output
File length before: 0
Size successfully changed
File length after:  329678
```

## <a name="see-also"></a>Voir aussi

[Gestion de fichiers](../../c-runtime-library/file-handling.md)<br/>
[_close](../../c-runtime-library/reference/close.md)<br/>
[_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_open, _wopen](../../c-runtime-library/reference/open-wopen.md)<br/>
