---
title: is_trivially_assignable, classe | Microsoft Docs
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
- type_traits/std::is_trivially_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b9ccc4937ec4f54756482fd8c3f7028506ca50d
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="istriviallyassignable-class"></a>is_trivially_assignable, classe

Teste si une valeur de type `From` peut être affectée de façon triviale au type `To`.

## <a name="syntax"></a>Syntaxe

```cpp
template <class To, class From>
struct is_trivially_assignable;
```

### <a name="parameters"></a>Paramètres

Pour le type de l’objet qui reçoit l’assignation.

À partir du type de l’objet qui fournit la valeur.

## <a name="remarks"></a>Notes

L’expression `declval<To>() = declval<From>()` doit être bien formée et le compilateur doit savoir qu’elle ne nécessite aucune opération non triviale. `From` et `To` doivent tous deux être des types complets, `void` ou des tableaux de limite inconnue.

## <a name="requirements"></a>Spécifications

**En-tête :** \<type_traits>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[<type_traits>](../standard-library/type-traits.md)<br/>
