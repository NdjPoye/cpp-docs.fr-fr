---
title: ftell, _ftelli64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ftelli64
- ftell
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
- _ftelli64
- ftell
dev_langs:
- C++
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d09d29abc4d1406bd85187ceb5c6661be98229be
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="ftell-ftelli64"></a>ftell, _ftelli64

Obtient la position actuelle d’un pointeur de fichier.

## <a name="syntax"></a>Syntaxe

```C
long ftell(
   FILE *stream
);
__int64 _ftelli64(
   FILE *stream
);
```

### <a name="parameters"></a>Paramètres

*Flux de données*<br/>
Cible **fichier** structure.

## <a name="return-value"></a>Valeur de retour

**ftell** et **_ftelli64** retourner la position actuelle du fichier. La valeur retournée par **ftell** et **_ftelli64** peut ne pas refléter le décalage d’octet physique pour les flux ouverts en mode texte, car le mode texte provoque la traduction des sauts de ligne de transport. Utilisez **ftell** avec [fseek](fseek-fseeki64.md) ou **_ftelli64** avec [_fseeki64](fseek-fseeki64.md) vers les emplacements de fichier correctement. En cas d’erreur, **ftell** et **_ftelli64** appellent le Gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, ces fonctions retournent-1 L et le jeu de **errno** à une des deux constantes, définis dans ERRNO. H. Le **EBADF** constante signifie la *flux* argument n’est pas une valeur de pointeur de fichier valide ou ne fait pas référence à un fichier ouvert. **EINVAL** signifie non valide *flux* argument a été passé à la fonction. Sur les appareils non compatibles avec la recherche (par exemple, les terminaux et les imprimantes), ou lorsque *flux* ne fait pas référence à un fichier ouvert, la valeur de retour n’est pas définie.

Pour plus d’informations sur ces codes de retour et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Notes

Le **ftell** et **_ftelli64** fonctions récupèrent la position actuelle du pointeur de fichier (le cas échéant) associée à *flux*. La position est exprimée sous la forme d’un décalage par rapport au début du flux.

Notez que quand un fichier est ouvert pour un ajout de données, la position de fichier actuelle est déterminée par la dernière opération d’E/S, pas par l’emplacement auquel l’écriture suivante se produirait. Par exemple, si un fichier est ouvert pour un ajout et que la dernière opération était une lecture, la position de fichier est le point où l’opération de lecture suivante commencerait, pas celui où l’écriture suivante démarrerait. (Quand un fichier est ouvert pour un ajout, la position de fichier est déplacée vers la fin du fichier avant toute opération d’écriture.) Si aucune opération d’E/S ne s’est produite sur un fichier ouvert pour un ajout, la position de fichier correspond au début du fichier.

En mode texte, Ctrl+Z est interprété comme un caractère de fin de fichier en entrée. Dans les fichiers ouverts en lecture/écriture, **fopen** et toutes les routines connexes d’un CTRL + Z à la fin du fichier et si possible de le supprimer. Pour cela, car il est à l’aide de la combinaison de **ftell** et [fseek](fseek-fseeki64.md) ou **_ftelli64** et [_fseeki64](fseek-fseeki64.md), pour se déplacer dans un fichier qui se termine par CTRL + Z peut provoquer **ftell** ou **_ftelli64** comportement incorrect vers la fin du fichier.

Cette fonction verrouille le thread appelant pendant l’exécution et est donc thread-safe. Pour une version sans verrouillage, voir **_ftell_nolock**.

## <a name="requirements"></a>Spécifications

|Fonction|En-tête requis|En-têtes facultatifs|
|--------------|---------------------|----------------------|
|**ftell**|\<stdio.h>|\<errno.h>|
|**_ftelli64**|\<stdio.h>|\<errno.h>|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemple

```C
// crt_ftell.c
// This program opens a file named CRT_FTELL.C
// for reading and tries to read 100 characters. It
// then uses ftell to determine the position of the
// file pointer and displays this position.

#include <stdio.h>

FILE *stream;

int main( void )
{
   long position;
   char list[100];
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )
   {
      // Move the pointer by reading data:
      fread( list, sizeof( char ), 100, stream );
      // Get position after read:
      position = ftell( stream );
      printf( "Position after trying to read 100 bytes: %ld\n",
              position );
      fclose( stream );
   }
}
```

```Output
Position after trying to read 100 bytes: 100
```

## <a name="see-also"></a>Voir aussi

[E/S de flux](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
