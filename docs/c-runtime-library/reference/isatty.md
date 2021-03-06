---
title: _isatty | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _isatty
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
- _isatty
dev_langs:
- C++
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4be35fce0a790751683a4bf8a0cceaf938fea82
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="isatty"></a>_isatty

Détermine si un descripteur de fichier est associé à un périphérique de caractères.

## <a name="syntax"></a>Syntaxe

```C
int _isatty( int fd );
```

### <a name="parameters"></a>Paramètres

*fd*<br/>
Descripteur de fichier qui fait référence au périphérique à tester.

## <a name="return-value"></a>Valeur de retour

**_isatty** retourne une valeur différente de zéro si le descripteur est associé à un périphérique en mode caractère. Dans le cas contraire, **_isatty** retourne 0.

## <a name="remarks"></a>Notes

Le **_isatty** fonction détermine si *fd* est associé à un périphérique en mode caractère (Terminal Server, console, imprimante ou port série).

Cette fonction valide le *fd* paramètre. Si *fd* est un pointeur de fichier incorrect, le Gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, la fonction retourne 0 et définit **errno** à **EBADF**.

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|
|-------------|---------------------|
|**_isatty**|\<io.h>|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliothèques

Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Exemple

```C
// crt_isatty.c
/* This program checks to see whether
* stdout has been redirected to a file.
*/

#include <stdio.h>
#include <io.h>

int main( void )
{
   if( _isatty( _fileno( stdout ) ) )
      printf( "stdout has not been redirected to a file\n" );
   else
      printf( "stdout has been redirected to a file\n");
}
```

### <a name="sample-output"></a>Résultat de l'exemple

```Output
stdout has not been redirected to a file
```

## <a name="see-also"></a>Voir aussi

[Gestion de fichiers](../../c-runtime-library/file-handling.md)<br/>
