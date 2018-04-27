---
title: _1, objet | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- _1
- std::_1
- functional/std::_1
dev_langs:
- C++
helpviewer_keywords:
- _1 object
ms.assetid: 30c3c480-ff31-4708-94be-7d0d65f243c9
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 340744b785ee1af14c2258ffd954d4ba6c92d217
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="1-object"></a>_1, objet

Espaces réservés pour les arguments remplaçables.

## <a name="syntax"></a>Syntaxe

```cpp
namespace placeholders {
    extern unspecified _1,
    _2, ... _M
 } // namespace placeholders (within std)
```

## <a name="remarks"></a>Notes

Les objets `_1, _2, ... _M` sont des espaces réservés désignant la première, deuxième,..., argument de mois, respectivement, dans un appel de fonction à un objet retourné par [lier](../standard-library/functional-functions.md#bind). Vous utilisez `_N` pour spécifier l’emplacement où le N-ième argument doit être inséré quand la liaison est évaluée.

Dans cette implémentation, la valeur de `M` est 20.

## <a name="example"></a>Exemple

```cpp
// std__functional_placeholder.cpp
// compile with: /EHsc
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std::placeholders;

void square(double x)
    {
    std::cout << x << "^2 == " << x * x << std::endl;
    }

void product(double x, double y)
    {
    std::cout << x << "*" << y << " == " << x * y << std::endl;
    }

int main()
    {
    double arg[] = {1, 2, 3};

    std::for_each(&arg[0], &arg[3], square);
    std::cout << std::endl;

    std::for_each(&arg[0], &arg[3], std::bind(product, _1, 2));
    std::cout << std::endl;

    std::for_each(&arg[0], &arg[3], std::bind(square, _1));

    return (0);
    }

```

```Output
1^2 == 1
2^2 == 4
3^2 == 9

1*2 == 2
2*2 == 4
3*2 == 6

1^2 == 1
2^2 == 4
3^2 == 9
```

## <a name="requirements"></a>Spécifications

**En-tête :** \<functional>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[bind](../standard-library/functional-functions.md#bind)<br/>
[is_placeholder, classe](../standard-library/is-placeholder-class.md)<br/>
