---
title: fsetpos | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- fsetpos
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
- fsetpos
dev_langs:
- C++
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ceacacbe029488995c47e305682b56751347591
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2018
---
# <a name="fsetpos"></a>fsetpos

Définit l’indicateur de position de flux.

## <a name="syntax"></a>Syntaxe

```C
int fsetpos(
   FILE *stream,
   const fpos_t *pos
);
```

### <a name="parameters"></a>Paramètres

*Flux de données*<br/>
Pointeur désignant la structure **FILE**.

*bons de commande*<br/>
Stockage de l’indicateur de position.

## <a name="return-value"></a>Valeur de retour

En cas de réussite, **fsetpos** retourne 0. En cas d’échec, la fonction retourne une valeur différente de zéro et définit **errno** à un des éléments suivants du manifeste de constantes (définies dans ERRNO. (H) : **EBADF**, ce qui signifie que le fichier n’est pas accessible ou l’objet qui *flux* pointe vers n’est pas une structure de fichier valide, ou **EINVAL**, ce qui signifie une valeur non valide pour *flux* ou *pos* a été passé. Si un paramètre non valide est passé, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).

Pour plus d’informations sur ces codes de retour et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Notes

Le **fsetpos** fonction définit l’indicateur de position de fichier pour *flux* à la valeur de *pos*, qui est obtenu dans un appel antérieur à **fgetpos**contre *flux*. La fonction efface l’indicateur de fin de fichier et annule les effets de [ungetc](ungetc-ungetwc.md) sur *flux*. Après avoir appelé **fsetpos**, l’opération suivante sur *flux* peut être entrée ou sortie.

## <a name="requirements"></a>Spécifications

|Fonction|En-tête requis|
|--------------|---------------------|
|**fsetpos**|\<stdio.h>|

Pour plus d’informations sur la compatibilité, voir consultez [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemple

Consultez l’exemple relatif à [fgetpos](fgetpos.md).

## <a name="see-also"></a>Voir aussi

[E/S de flux](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
