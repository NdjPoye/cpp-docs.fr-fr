---
title: is_pod, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_pod
dev_langs:
- C++
helpviewer_keywords:
- is_pod class
- is_pod
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b52479cc433f59d76dd40cfb752550e51652892d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="ispod-class"></a>is_pod, classe

Teste si le type est POD.

## <a name="syntax"></a>Syntaxe

```cpp
template <class T>
struct is_pod;
```

### <a name="parameters"></a>Paramètres

*T* type à interroger.

## <a name="remarks"></a>Notes

`is_pod<T>::value` est `true` si le type *T* est Plain Old Data (POD). Sinon, il est `false`.

Les types arithmétiques, les types énumération, les types pointeur et les pointeurs vers des types de membres sont des types POD.

Une version cv-qualified d'un type POD est elle-même un type POD.

Un tableau de POD est lui-même POD.

Une structure ou une union, dont tous les membres de données non statiques sont POD, est elle-même POD si elle n'a :

- aucun constructeur déclaré par l'utilisateur ;

- aucun membre de données non statiques privé ou protégé ;

- aucune classe de base ;

- aucune fonction virtuelle ;

- aucun membre de données non statiques de type référence ;

- aucun opérateur d'assignation de copie défini par l'utilisateur ;

- aucun destructeur défini par l'utilisateur.

Par conséquent, vous pouvez générer de manière récursive des structs et des tableaux POD qui contiennent des structs et des tableaux POD.

## <a name="example"></a>Exemple

```cpp
// std__type_traits__is_pod.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial {
    int val;
};

struct throws {
    throws() {}  // User-declared ctor, so not POD

    int val;
};

int main() {
    std::cout << "is_pod<trivial> == " << std::boolalpha
        << std::is_pod<trivial>::value << std::endl;
    std::cout << "is_pod<int> == " << std::boolalpha
        << std::is_pod<int>::value << std::endl;
    std::cout << "is_pod<throws> == " << std::boolalpha
        << std::is_pod<throws>::value << std::endl;

    return (0);
}
```

```Output
is_pod<trivial> == true
is_pod<int> == true
is_pod<throws> == false
```

## <a name="requirements"></a>Spécifications

**En-tête :** \<type_traits>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[<type_traits>](../standard-library/type-traits.md)<br/>
