---
title: '&lt;random&gt;, fonctions | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
caps.latest.revision: 10
manager: ghogen
ms.openlocfilehash: e3c5dba462b45589005a996e6226330882b29b15
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="ltrandomgt-functions"></a>&lt;random&gt;, fonctions

## <a name="generate_canonical"></a>  generate_canonical

Retourne une valeur à virgule flottante à partir d'une séquence aléatoire.

> [!NOTE]
> La norme C++ ISO spécifie que cette fonction doit retourner des valeurs dans la plage [`0`, `1`). Visual Studio n'est pas encore conforme à cette contrainte. Comme solution de contournement pour générer des valeurs dans cette plage, utilisez [uniform_real_distribution](../standard-library/uniform-real-distribution-class.md).

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>Paramètres

`RealType` Type intégral à virgule flottante. Pour connaître les types possibles, consultez [\<random>](../standard-library/random.md).

`Bits` Le Générateur de nombres aléatoires.

`Gen` Le Générateur de nombres aléatoires.

### <a name="remarks"></a>Notes

La fonction avec modèle appelle l'élément `operator()` de `Gen` à plusieurs reprises et compresse les valeurs retournées dans une valeur à virgule flottante `x` de type `RealType` jusqu'à ce qu'elle ait recueilli le nombre spécifié de bits de mantisse dans `x`. Le nombre spécifié est la plus petite valeur de `Bits` (qui doit être différente de zéro) et le nombre complet de bits de mantisse dans `RealType`. Le premier appel fournit les bits d'ordre le plus bas. La fonction retourne `x`.

## <a name="see-also"></a>Voir aussi

[\<random>](../standard-library/random.md)<br/>
