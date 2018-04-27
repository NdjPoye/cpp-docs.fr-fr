---
title: make_unsigned, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::make_unsigned
dev_langs:
- C++
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aba0421ab55d5cf30b38f69e58123fbd4056d16f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="makeunsigned-class"></a>make_unsigned, classe

Rend le type ou le plus petit type non signé supérieur ou égal en taille au type.

## <a name="syntax"></a>Syntaxe

```cpp
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```

### <a name="parameters"></a>Paramètres

|Paramètre|Description|
|---------------|-----------------|
|`T`|Type à modifier.|

## <a name="remarks"></a>Notes

Une instance du modificateur de type contient un type modifié qui est `T` si `is_unsigned<T>` contient la valeur true. Dans le cas contraire, il s'agit du plus petit type signé `ST` pour lequel `sizeof (T) <= sizeof (ST)`.

## <a name="requirements"></a>Spécifications

**En-tête :** \<type_traits>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[<type_traits>](../standard-library/type-traits.md)<br/>
