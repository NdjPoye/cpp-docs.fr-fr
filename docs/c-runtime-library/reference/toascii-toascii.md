---
title: toascii, __toascii | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- __toascii
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __toascii
- toascii
- ctype/toascii
- ctype/__toascii
dev_langs:
- C++
helpviewer_keywords:
- toascii function
- string conversion, to ASCII characters
- __toascii function
- ASCII characters, converting to
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf4c29934d22d3f20d79650faa406f217ffdd4c6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="toascii-toascii"></a>toascii, __toascii

Convertit des caractères au format ASCII 7 bits par troncation.

## <a name="syntax"></a>Syntaxe

```C
int __toascii(
   int c
);
#define toascii __toascii
```

### <a name="parameters"></a>Paramètres

*c*  
Caractère à convertir.

## <a name="return-value"></a>Valeur de retour

`__toascii` Convertit la valeur de *c* de plage pour le code ASCII 7 bits et retourne le résultat. Il n’existe aucune valeur de retour réservée pour indiquer une erreur.

## <a name="remarks"></a>Notes

La routine `__toascii` convertit le caractère donné en caractère ASCII en le tronquant sur 7 bits de poids faible. Aucune autre transformation n’est appliquée.

La routine `__toascii` est définie en tant que macro, sauf si la macro de préprocesseur _CTYPE_DISABLE_MACROS est définie. Pour la compatibilité descendante, `toascii` est défini comme macro uniquement lorsque [&#95; &#95; STDC &#95; &#95; ](../../preprocessor/predefined-macros.md) n’est pas défini ou est défini sur 0 ; sinon, il n’est pas défini.

## <a name="requirements"></a>Configuration requise

|Routine|En-tête requis|
|-------------|---------------------|
|`toascii`, `__toascii`|C : \<ctype.h><br /><br /> C++ : \<cctype> ou \<ctype.h>|

La macro `toascii` est une extension POSIX, alors que `__toascii` est une implémentation propre à Microsoft de l’extension POSIX. Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.

## <a name="see-also"></a>Voir aussi

[Conversion de données](../../c-runtime-library/data-conversion.md)   
[is, isw, routines](../../c-runtime-library/is-isw-routines.md)   
[to, fonctions](../../c-runtime-library/to-functions.md)