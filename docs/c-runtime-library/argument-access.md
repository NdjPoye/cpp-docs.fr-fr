---
title: Accès aux arguments | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2018
ms.technology:
- cpp-standard-libraries
ms.topic: article
f1_keywords:
- c.arguments
dev_langs:
- C++
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: afef1300637f7a31755eb9408f9d33d9504475a1
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2018
---
# <a name="argument-access"></a>Accès aux arguments

Les macros **va_arg**, **va_end** et **va_start** fournissent l’accès aux arguments de fonction quand le nombre d’arguments est variable. Ces macros sont définies dans \<stdarg.h> pour la compatibilité ANSI/ISO C et dans \<varargs.h> pour la compatibilité avec UNIX System V.

## <a name="argument-access-macros"></a>Macros d’accès à un argument

|Macro|Utilisez|
|-----------|-------------------------------|
|[va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Récupérer un argument dans la liste|
|[va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Réinitialiser le pointeur|
|[va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Définir le pointeur au début de la liste d’arguments|

## <a name="see-also"></a>Voir aussi

[Routines du runtime C universel par catégorie](../c-runtime-library/run-time-routines-by-category.md)
