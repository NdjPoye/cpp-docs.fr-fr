---
title: _get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_invalid_parameter_handler
- stdlib/_get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
- stdlib/_get_thread_local_invalid_parameter_handler
dev_langs:
- C++
helpviewer_keywords:
- _get_thread_local_invalid_parameter_handler function
- _get_invalid_parameter_handler function
ms.assetid: a176da0e-38ca-4d99-92bb-b0e2b8072f53
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a3e4df593e027c77909f6d3d1ea7c7a106799a9
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2018
---
# <a name="getinvalidparameterhandler-getthreadlocalinvalidparameterhandler"></a>_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler

Obtient la fonction qui est appelée quand la bibliothèque CRT détecte un argument non valide.

## <a name="syntax"></a>Syntaxe

```C
_invalid_parameter_handler _get_invalid_parameter_handler(void);
_invalid_parameter_handler _get_thread_local_invalid_parameter_handler(void);
```

## <a name="return-value"></a>Valeur de retour

Un pointeur désignant la fonction de gestionnaire de paramètres non valides définie, ou un pointeur Null si aucune n’a été définie.

## <a name="remarks"></a>Notes

Le **_get_invalid_parameter_handler** extrait la Gestionnaire de paramètre non valide global. Elle retourne un pointeur Null si aucun gestionnaire de paramètres non valides global n’a été défini. De même, la **_get_thread_local_invalid_parameter_handler** Obtient le Gestionnaire de paramètre non valide de locales de thread actuel du thread qu’elle est appelée pour, ou un pointeur null si aucun gestionnaire n’a été défini. Pour plus d’informations sur la façon de définir des gestionnaires de paramètres non valides globaux et locaux de thread, consultez [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).

Le pointeur de la fonction de gestionnaire de paramètres non valides retourné a le type suivant :

```C
typedef void (__cdecl* _invalid_parameter_handler)(
    wchar_t const*,
    wchar_t const*,
    wchar_t const*,
    unsigned int,
    uintptr_t
    );
```

Pour plus d’informations sur le gestionnaire de paramètres non valides, consultez le prototype dans [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|
|-------------|---------------------|
|**_get_invalid_parameter_handler**, **_get_thread_local_invalid_parameter_handler**|C : \<stdlib.h><br /><br /> C++ : \<cstdlib> ou \<stdlib.h>|

Le **_get_invalid_parameter_handler** et **_get_thread_local_invalid_parameter_handler** fonctions sont spécifiques de Microsoft. Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Voir aussi

[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[Versions à la sécurité améliorée des fonctions CRT](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)<br/>
