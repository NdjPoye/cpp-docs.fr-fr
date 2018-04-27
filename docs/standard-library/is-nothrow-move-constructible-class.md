---
title: is_nothrow_move_constructible, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_move_constructible
ms.assetid: d186d97b-7b89-470a-8d30-993046a83379
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f3bdb38107e5776a2f523f7c91c706fee1a0ba1f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="isnothrowmoveconstructible-class"></a>is_nothrow_move_constructible, classe

Teste si le type a un constructeur de déplacement **nothrow**.

## <a name="syntax"></a>Syntaxe

```cpp
template <class Ty>
struct is_nothrow_move_constructible;
```

### <a name="parameters"></a>Paramètres

`Ty` Type à interroger.

## <a name="remarks"></a>Notes

Une instance du prédicat de type a la valeur true si le type `Ty` a un constructeur de déplacement nothrow. Sinon, sa valeur est false.

## <a name="requirements"></a>Spécifications

**En-tête :** \<type_traits>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[<type_traits>](../standard-library/type-traits.md)<br/>
