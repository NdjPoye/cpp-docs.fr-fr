---
title: is_move_constructible, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 35e7bb78b1d2f2bc228230ef7d543aabb4506ae8
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="ismoveconstructible-class"></a>is_move_constructible, classe

Teste si le type a un constructeur de déplacement.

## <a name="syntax"></a>Syntaxe

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Paramètres

T le type à évaluer

## <a name="remarks"></a>Notes

Prédicat de type qui a la valeur true si le type `T` est constructible par une opération de déplacement. Ce prédicat équivaut à `is_constructible<T, T&&>`.

## <a name="requirements"></a>Spécifications

**En-tête :** \<type_traits>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[<type_traits>](../standard-library/type-traits.md)<br/>
