---
title: towctrans | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- towctrans
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
- towctrans
dev_langs:
- C++
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a1e3029fc9d33df93e13e6fd0a8e9e8d8da168b0
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2018
---
# <a name="towctrans"></a>towctrans

Transforme un caractère.

## <a name="syntax"></a>Syntaxe

```C
wint_t towctrans(
   wint_t c,
   wctrans_t category
);
```

### <a name="parameters"></a>Paramètres

*c*<br/>
Caractère que vous souhaitez transformer.

*category*<br/>
Identificateur qui contient la valeur de retour de [wctrans](wctrans.md).

## <a name="return-value"></a>Valeur de retour

Le caractère *c*, après **towctrans** utilisé dans la règle de transformation *catégorie*.

## <a name="remarks"></a>Notes

La valeur de *catégorie* doit avoir été retourné par un appel réussi précédemment à [wctrans](wctrans.md).

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|
|-------------|---------------------|
|**towctrans**|\<wctype.h>|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemple

Consultez **wctrans** pour obtenir un exemple qui utilise **towctrans**.

## <a name="see-also"></a>Voir aussi

[Conversion de données](../../c-runtime-library/data-conversion.md)<br/>
