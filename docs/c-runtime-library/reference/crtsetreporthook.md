---
title: _CrtSetReportHook | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtSetReportHook
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
- _CrtSetReportHook
- CrtSetReportHook
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ef76fe0b7befb99b5bf0e8bb69fa1a1229782de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="crtsetreporthook"></a>_CrtSetReportHook

Installe une fonction de création de rapports définie par le client en la raccordant au processus de création de rapports de débogage du runtime C (version de débogage uniquement).

## <a name="syntax"></a>Syntaxe

```C
_CRT_REPORT_HOOK _CrtSetReportHook(
   _CRT_REPORT_HOOK reportHook
);
```

### <a name="parameters"></a>Paramètres

*reportHook*<br/>
Nouvelle fonction de création de rapports définie par le client à raccorder au processus de création de rapports de débogage du runtime C.

## <a name="return-value"></a>Valeur de retour

Retourne la fonction de création de rapports précédente définie par le client.

## <a name="remarks"></a>Notes

**_CrtSetReportHook** permet à une application d’utiliser sa propre déclaration de fonction dans la bibliothèque de débogage du runtime C processus de création de rapports. Ainsi, chaque fois que [_CrtDbgReport](crtdbgreport-crtdbgreportw.md) est appelé pour générer un rapport de débogage, la fonction de création de rapports de l’application est appelée en premier. Cette fonctionnalité permet à une application effectuer des opérations telles que le filtrage des rapports de débogage et elle peut se concentrer sur les types d’allocation spécifiques ou envoyer un rapport à des destinations non disponibles à l’aide de **_CrtDbgReport**. Lorsque [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à **_CrtSetReportHook** sont supprimés lors du prétraitement.

Pour une version plus robuste de **_CrtSetReportHook**, consultez [_CrtSetReportHook2](crtsetreporthook2-crtsetreporthookw2.md).

Le **_CrtSetReportHook** fonction installe la nouvelle déclaration de fonction spécifiée dans défini par le client *reportHook* et retourne le raccordement défini par le client précédent. L’exemple suivant montre comment un raccordement de rapport défini par le client doit être prototypé :

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

où *reportType* est le type de rapport de débogage (**_CRT_WARN**, **_CRT_ERROR**, ou **_CRT_ASSERT**), *demessage* est le message utilisateur de débogage entièrement assemblé doit être contenu dans le rapport, et **returnValue** est la valeur spécifiée par le client défini reporting (fonction) qui doit être retournée par **_ CrtDbgReport**. Pour obtenir une description complète des types de rapports disponibles, consultez la fonction [_CrtSetReportMode](crtsetreportmode.md).

Si la fonction de rapport défini par le client gère complètement le message de débogage telles qu’aucun rapport supplémentaire n’est requise, la fonction doit retourner **TRUE**. Lorsque la fonction retourne **FALSE**, **_CrtDbgReport** est appelée pour générer le rapport de débogage à l’aide des paramètres actuels pour le type de rapport, le mode et le fichier. En outre, en spécifiant le **_CrtDbgReport** retourner la valeur de **returnValue**, l’application peut également contrôler si un arrêt du débogage. Pour obtenir une description complète de la façon dont le rapport de débogage est configuré et généré, consultez **_CrtSetReportMode**, [_CrtSetReportFile](crtsetreportfile.md), et **_CrtDbgReport**.

Pour plus d’informations sur l’utilisation d’autres fonctions d’exécution compatibles avec le raccordement et sur l’écriture de vos propres fonctions de raccordement définies par le client, consultez [Écriture de fonctions de raccordement de débogage](/visualstudio/debugger/debug-hook-function-writing).

> [!NOTE]
> Si votre application est compilée avec **/CLR** et la fonction de création de rapports est appelée après que l’application a quitté principale, le CLR lève une exception si la fonction de création de rapports appelle les fonctions CRT.

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|
|-------------|---------------------|
|**_CrtSetReportHook**|\<crtdbg.h>|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliothèques

Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Voir aussi

[Routines de débogage](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetReportHook](crtgetreporthook.md)<br/>
