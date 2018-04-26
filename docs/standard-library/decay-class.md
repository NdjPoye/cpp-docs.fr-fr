---
title: decay, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::decay
dev_langs:
- C++
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f33d7dd901d4da0c6f30cfabaa2853897dd8635e
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="decay-class"></a>decay, classe

Produit le type passé par la valeur. Transforme un type en non-référence, non-const ou non-volatile, ou crée un pointeur vers le type à partir d’une fonction ou d’un type de tableau.

## <a name="syntax"></a>Syntaxe

```cpp
template <class T>
struct decay;

template <class T>
using decay_t = typename decay<T>::type;
```

### <a name="parameters"></a>Paramètres

`T` Le type à modifier.

## <a name="remarks"></a>Notes

Utilisez le modèle de décomposition pour produire le type résultant comme si le type avait été passé comme argument par la valeur. Un typedef de membre de la classe de modèle `type` contient un type modifié qui est défini au cours des étapes suivantes :

- Le type `U` est défini en tant que `remove_reference<T>::type`.

- Si `is_array<U>::value` a la valeur true, le type modifié `type` est `remove_extent<U>::type *`.

- Sinon, si `is_function<U>::value` a la valeur true, le type modifié `type` est `add_pointer<U>::type`.

- Sinon, le type modifié `type` est `remove_cv<U>::type`.

## <a name="requirements"></a>Spécifications

**En-tête :** \<type_traits>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[<type_traits>](../standard-library/type-traits.md)<br/>
