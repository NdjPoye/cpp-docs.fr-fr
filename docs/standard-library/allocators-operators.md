---
title: '&lt;allocators&gt;, opérateurs | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
dev_langs:
- C++
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: d6d69d07c8b16d2749c7ac62eb290f180b1e1b09
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt;, opérateurs

Ce sont les fonctions d’opérateur de modèle global définies dans &lt;allocateurs&gt;. Pour les fonctions d’opérateur de membre de classe, consultez la documentation de la classe.

|||
|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator!=

Vérifie l'inégalité entre les objets allocateurs d'une classe spécifiée.

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Paramètres

|Paramètre|Description|
|---------------|-----------------|
|`left`|Un des objets allocateur dont l’inégalité doit être vérifiée.|
|`right`|Un des objets allocateur dont l’inégalité doit être vérifiée.|

### <a name="return-value"></a>Valeur de retour

**true** si les objets allocateur ne sont pas égaux ; **false** si les objets allocateur sont égaux.

### <a name="remarks"></a>Notes

L’opérateur de modèle retourne `!(left == right)`.

## <a name="op_eq_eq"></a>  operator==

Vérifie l'égalité entre les objets allocateurs d'une classe spécifiée.

```cpp
template <class Type, class Sync>
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Paramètres

|Paramètre|Description|
|---------------|-----------------|
|`left`|Un des objets allocateur dont l’égalité doit être vérifiée.|
|`right`|Un des objets allocateur dont l’égalité doit être vérifiée.|

### <a name="return-value"></a>Valeur de retour

**true** si les objets allocateur sont égaux ; **false** si les objets allocateur ne sont pas égaux.

### <a name="remarks"></a>Notes

Cet opérateur de modèle retourne `left.equals(right)`.

## <a name="see-also"></a>Voir aussi

[\<allocators>](../standard-library/allocators-header.md)
