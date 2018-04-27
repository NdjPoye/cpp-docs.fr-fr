---
title: duration_values, structure | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- chrono/std::chrono::duration_values
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
dev_langs:
- C++
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a2cba8fd6fe3e4763e05dc0cc897e8a0b968d611
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="durationvalues-structure"></a>duration_values, structure

Fournit des valeurs spécifiques pour le paramètre de modèle [duration](../standard-library/duration-class.md) `Rep`.

## <a name="syntax"></a>Syntaxe

```cpp
template <class Rep>
struct duration_values;
```

## <a name="members"></a>Membres

### <a name="public-methods"></a>M&#233;thodes publiques

|Nom|Description|
|----------|-----------------|
|[max](#max)|Static. Spécifie la limite supérieure pour une valeur de type `Rep`.|
|[min](#min)|Static. Spécifie la limite inférieure pour une valeur de type `Rep`.|
|[Zéro](#zero)|Static. Retourne `Rep(0)`.|

## <a name="requirements"></a>Spécifications

**En-tête :** \<chrono >

**Espace de noms :** std::chrono

## <a name="max"></a>  duration_values::max

Méthode statique qui retourne la limite supérieure des valeurs de type `Ref`.

```cpp
static constexpr Rep max();
```

### <a name="return-value"></a>Valeur de retour

Retourne `numeric_limits<Rep>::max()`.

### <a name="remarks"></a>Notes

Quand `Rep` est un type défini par l’utilisateur, la valeur de retour doit être supérieure à [duration_values::zero](#zero).

## <a name="min"></a>  duration_values::min

Méthode statique qui retourne la limite inférieure des valeurs de type `Ref`.

```cpp
static constexpr Rep min();
```

### <a name="return-value"></a>Valeur de retour

Retourne `numeric_limits<Rep>::lowest()`.

### <a name="remarks"></a>Notes

Quand `Rep` est un type défini par l’utilisateur, la valeur de retour doit être inférieure ou égale à [duration_values::zero](#zero).

## <a name="zero"></a>  duration_values::zero

Retourne `Rep(0)`.

```cpp
static constexpr Rep zero();
```

### <a name="remarks"></a>Notes

Quand `Rep` est un type défini par l'utilisateur, la valeur de retour doit représenter l'infini additif.

## <a name="see-also"></a>Voir aussi

[Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono>](../standard-library/chrono.md)<br/>
