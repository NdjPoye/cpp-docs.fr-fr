---
title: _aligned_offset_malloc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_offset_malloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _aligned_offset_malloc
- aligned_offset_malloc
dev_langs:
- C++
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bcc5fe0d786c7fdb04455f231cc3c8e60b53a22
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="alignedoffsetmalloc"></a>_aligned_offset_malloc

Alloue de la mémoire sur une limite d'alignement spécifiée.

## <a name="syntax"></a>Syntaxe

```C
void * _aligned_offset_malloc(
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Paramètres

*size*<br/>
Taille de l'allocation de mémoire demandée.

*Alignement*<br/>
Valeur d'alignement, qui doit être un entier à puissance 2.

*offset*<br/>
Décalage dans l'allocation de mémoire pour forcer l'alignement.

## <a name="return-value"></a>Valeur de retour

Un pointeur vers le bloc de mémoire qui a été alloué ou **NULL** si l’opération a échoué.

## <a name="remarks"></a>Notes

**_aligned_offset_malloc** est utile dans les situations où l’alignement est nécessaire sur un élément imbriqué ; par exemple, si l’alignement était nécessaire sur une classe imbriquée.

**_aligned_offset_malloc** est basée sur **malloc**; pour plus d’informations, consultez [malloc](malloc.md).

**_aligned_offset_malloc** est marquée `__declspec(noalias)` et `__declspec(restrict)`, ce qui signifie que la fonction ne peut ne pas modifier les variables globales et que le pointeur retourné n’est pas un alias. Pour plus d’informations, consultez [noalias](../../cpp/noalias.md) et [restrict](../../cpp/restrict.md).

Cette fonction affecte **errno** à **ENOMEM** si l’allocation de mémoire a échoué ou si la taille demandée était supérieure à **_HEAP_MAXREQ**. Pour plus d’informations sur **errno**, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). En outre, **_aligned_offset_malloc** valide ses paramètres. Si *alignement* n’est pas une puissance de 2 ou si *offset* est supérieur ou égal à *taille* et différent de zéro, cette fonction appelle le Gestionnaire de paramètre non valide, comme décrit dans [ Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, cette fonction retourne **NULL** et définit **errno** à **EINVAL**.

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|
|-------------|---------------------|
|**_aligned_offset_malloc**|\<malloc.h>|

## <a name="example"></a>Exemple

Pour plus d’informations, consultez [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Voir aussi

[Alignement des données](../../c-runtime-library/data-alignment.md)<br/>
