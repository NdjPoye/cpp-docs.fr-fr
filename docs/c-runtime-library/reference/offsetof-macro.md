---
title: offsetof Macro | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
apitype: DLLExport
f1_keywords:
- offsetof
dev_langs:
- C++
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 686de81ecfd4216f3011c93d3bf9be1bfdc55365
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2018
---
# <a name="offsetof-macro"></a>offsetof, macro

Récupère le décalage d'un membre au début de sa structure parent.

## <a name="syntax"></a>Syntaxe

```C
size_t offsetof(
   structName,
   memberName
);
```

### <a name="parameters"></a>Paramètres

*structName*<br/>
Nom de la structure de données parent.

*Nom de membre*<br/>
Nom du membre dans la structure de données parent pour lequel le décalage doit être déterminé.

## <a name="return-value"></a>Valeur de retour

**offsetof** retourne l’offset en octets du membre spécifié à partir du début de sa structure de données parent. Il n'est pas défini pour les champs de bits.

## <a name="remarks"></a>Notes

Le **offsetof** macro retourne le décalage en octets de *memberName* à partir du début de la structure spécifiée par *structName* en tant que valeur de type **size_ t**. Vous pouvez spécifier les types avec le **struct** (mot clé).

> [!NOTE]
> **offsetof** n’est pas une fonction et ne peut pas être décrite à l’aide d’un prototype C.

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|
|-------------|---------------------|
|**offsetof**|\<stddef.h>|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliothèques

Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Voir aussi

[Allocation de mémoire](../../c-runtime-library/memory-allocation.md)<br/>
