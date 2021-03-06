---
title: '&lt;scoped_allocator&gt;, opérateurs | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
dev_langs:
- C++
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
ms.openlocfilehash: 66cf60dd3d70719fe42645215b1190c9fb752ff3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="ltscopedallocatorgt-operators"></a>&lt;scoped_allocator&gt;, opérateurs

|||
|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator!=

Teste si deux objets `scoped_allocator_adaptor` sont inégaux.

```cpp
template <class Outer, class... Inner>
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>Paramètres

`left` Gauche `scoped_allocator_adaptor` objet.

`right` Droite `scoped_allocator_adaptor` objet.

### <a name="return-value"></a>Valeur de retour

`!(left == right)`

## <a name="op_eq_eq"></a>  operator==

Teste si deux objets `scoped_allocator_adaptor` sont égaux.

```cpp
template <class Outer, class... Inner>
bool operator==(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>Paramètres

`left` Gauche `scoped_allocator_adaptor` objet.

`right` Droite `scoped_allocator_adaptor` objet.

### <a name="return-value"></a>Valeur de retour

`left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`

## <a name="see-also"></a>Voir aussi

[<scoped_allocator>](../standard-library/scoped-allocator.md)<br/>
