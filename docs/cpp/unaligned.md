---
title: __unaligned | Documents Microsoft
ms.custom: 
ms.date: 03/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __unaligned_cpp
dev_langs:
- C++
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a9f30e2b268be6f9398cf0af40d66b786c7cdca9
ms.sourcegitcommit: eb246547c7c9adc7d7ac4083ef09bf6e54dec914
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2018
---
# <a name="unaligned"></a>__unaligned

**Spécifique à Microsoft**. Lorsque vous déclarez un pointeur avec le modificateur `__unaligned`, le compilateur suppose que le pointeur adresse des données non alignées. Par conséquent, approprié à la plateforme de code est généré pour gérer des lectures non alignés et écrit par l’intermédiaire du pointeur.

## <a name="remarks"></a>Notes

Ce modificateur décrit l’alignement des données traitées par le pointeur ; le pointeur lui-même est considéré comme aligné.

La nécessité pour le `__unaligned` mot clé varie selon la plate-forme et l’environnement. Échec pour marquer des données de façon appropriée peut entraîner des problèmes, allant de trop handicaper les performances pour les défaillances matérielles. Le `__unaligned` modificateur n’est pas valide pour le x86 plateforme.

Pour plus d'informations sur l'alignement, consultez :

- [align](../cpp/align-cpp.md)

- [__alignof, opérateur](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (Alignement des membres de la structure)](../build/reference/zp-struct-member-alignment.md)

- [Exemples d’alignement de structure](../build/examples-of-structure-alignment.md)

## <a name="see-also"></a>Voir aussi

[Mots clés](../cpp/keywords-cpp.md)
