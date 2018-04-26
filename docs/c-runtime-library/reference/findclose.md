---
title: _findclose | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _findclose
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _findclose
- findclose
dev_langs:
- C++
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 89c1f515bb072c649a93b77e49b500ea4636e423
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2018
---
# <a name="findclose"></a>_findclose

Ferme le handle de recherche spécifié et libère les ressources associées.

## <a name="syntax"></a>Syntaxe

```C
int _findclose(
   intptr_t handle
);
```

### <a name="parameters"></a>Paramètres

*Handle*<br/>
Handle de recherche renvoyé par un appel précédent à **_findfirst**.

## <a name="return-value"></a>Valeur de retour

En cas de réussite, **_findclose** retourne 0. Sinon, elle retourne -1 et définit **errno** à **ENOENT**, indiquant que plus aucune mise en correspondance des fichiers a été trouvé.

## <a name="requirements"></a>Spécifications

|Fonction|En-tête requis|
|--------------|---------------------|
|**_findclose**|\<io.h>|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Voir aussi

[Appels système](../../c-runtime-library/system-calls.md)<br/>
[Fonctions de recherche de nom de fichier](../../c-runtime-library/filename-search-functions.md)<br/>
