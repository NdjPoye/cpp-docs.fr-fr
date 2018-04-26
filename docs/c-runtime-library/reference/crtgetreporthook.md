---
title: _CrtGetReportHook | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _CrtGetReportHook
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
- CrtGetReportHook
- _CrtGetReportHook
dev_langs:
- C++
helpviewer_keywords:
- CrtGetReportHook function
- _CrtGetReportHook function
ms.assetid: 922758ed-7edd-4359-9c92-0535192dc11a
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b1e499b1663cbde3bcaa0a01a26e96d544ca390
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2018
---
# <a name="crtgetreporthook"></a>_CrtGetReportHook

Récupère la fonction de création de rapports définie par le client pour la raccorder au runtime C pour le processus de création de rapports de débogage (version de débogage uniquement).

## <a name="syntax"></a>Syntaxe

```C
_CRT_REPORT_HOOK _CrtGetReportHook( void );
```

## <a name="return-value"></a>Valeur de retour

Retourne la fonction de création de rapports actuelle définie par le client.

## <a name="remarks"></a>Notes

**_CrtGetReportHook** permet à une application récupérer la fonction en cours de création de rapports pour la bibliothèque de débogage du runtime C processus de création de rapports.

Pour plus d’informations sur l’utilisation d’autres fonctions d’exécution compatibles avec le raccordement et sur l’écriture de vos propres fonctions de raccordement définies par le client, consultez [Écriture de fonctions de raccordement de débogage](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|
|-------------|---------------------|
|**_CrtGetReportHook**|\<crtdbg.h>|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliothèques

Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Exemple

Pour obtenir un exemple montrant comment utiliser **_CrtSetReportHook**, consultez [rapport](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/report).

## <a name="see-also"></a>Voir aussi

[Routines de débogage](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetReportHook](crtsetreporthook.md)<br/>
