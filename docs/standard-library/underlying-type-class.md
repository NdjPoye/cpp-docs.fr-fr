---
title: underlying_type, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- type_traits/std::underlying_type
dev_langs:
- C++
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52bf41cdcb40c88f32adc6d0384bea60f5997286
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="underlyingtype-class"></a>underlying_type, classe

Génère le type intégral sous-jacent pour un type d’énumération.

## <a name="syntax"></a>Syntaxe

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>Paramètres

`T` Le type à modifier.

## <a name="remarks"></a>Notes

Le typedef de membre `type` de la classe de modèle désigne le type intégral sous-jacent de `T`, lorsque `T` est un type d’énumération ; sinon il n’existe aucun typedef de membre `type`.

## <a name="requirements"></a>Spécifications

**En-tête :** \<type_traits>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[<type_traits>](../standard-library/type-traits.md)<br/>
