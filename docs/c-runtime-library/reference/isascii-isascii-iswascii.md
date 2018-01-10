---
title: isascii, __isascii, iswascii | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- iswascii
- __isascii
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- iswascii
- istascii
- __isascii
- _istascii
- isascii
- ctype/isascii
- ctype/__isascii
- corecrt_wctype/iswascii
dev_langs: C++
helpviewer_keywords:
- __isascii function
- _isascii function
- isascii function
- _istascii function
- istascii function
- iswascii function
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3858955a1409842d80439401d6c689c06f6c86f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="isascii-isascii-iswascii"></a>isascii, __isascii, iswascii

Détermine si un caractère particulier est un caractère ASCII.

## <a name="syntax"></a>Syntaxe

```C
int __isascii(
   int c
);
int iswascii(
   wint_t c
);

#define isascii __isascii
```

### <a name="parameters"></a>Paramètres

*c*  
Entier à tester.

## <a name="return-value"></a>Valeur de retour

Chacune de ces routines retourne une valeur différente de zéro si `c` est une représentation particulière d’un caractère ASCII. `__isascii`Retourne une valeur différente de zéro si `c` est un caractère ASCII (dans la plage 0 x 00 – 0x7F). `iswascii` retourne une valeur différente de zéro si `c` est une représentation de caractères larges d’un caractère ASCII. Chacune de ces routines retourne 0 si `c` ne répond pas à la condition de test.

## <a name="remarks"></a>Notes

`__isascii` et `iswascii` sont implémentées en tant que macros, sauf si la macro de préprocesseur _CTYPE_DISABLE_MACROS est définie.

Pour la compatibilité descendante, `isascii` est implémenté comme un uniquement si de macro [&#95; &#95; STDC &#95; &#95; ](../../preprocessor/predefined-macros.md) n’est pas défini ou est défini sur 0 ; sinon, il n’est pas défini.

### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique

|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_istascii`|`__isascii`|`__isascii`|`iswascii`|

## <a name="requirements"></a>Configuration requise

|Routine|En-tête requis|
|-------------|---------------------|
|`isascii`, `__isascii`|C : \<ctype.h><br /><br /> C++ : \<cctype> ou \<ctype.h>|
|`iswascii`|C : \<wctype.h>, \<ctype.h> ou \<wchar.h><br /><br /> C++ : \<cwctype>, \<cctype>, \<wctype.h>, \<ctype.h> ou \<wchar.h>|

Les fonctions `isascii`, `__isascii` et `iswascii` sont des fonctions fournies par Microsoft. Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.

## <a name="see-also"></a>Voir aussi

[Classifications des caractères](../../c-runtime-library/character-classification.md)   
[Paramètres régionaux](../../c-runtime-library/locale.md)   
[is, isw, routines](../../c-runtime-library/is-isw-routines.md)