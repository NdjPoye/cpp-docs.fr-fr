---
title: '&lt;type_traits&gt;, fonctions | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- type_traits/std::is_assignable
- type_traits/std::is_copy_assignable
- type_traits/std::is_copy_constructible
- type_traits/std::is_default_constructible
- type_traits/std::is_move_assignable
- type_traits/std::is_move_constructible
- type_traits/std::is_nothrow_move_assignable
- type_traits/std::is_trivially_copy_assignable
- type_traits/std::is_trivially_move_assignable
- type_traits/std::is_trivially_move_constructible
ms.assetid: dce4492f-f3e4-4d5e-bdb4-5875321254ec
helpviewer_keywords:
- std::is_assignable
- std::is_copy_assignable
- std::is_copy_constructible
- std::is_default_constructible
- std::is_move_assignable
- std::is_move_constructible
- std::is_nothrow_move_assignable
- std::is_trivially_copy_assignable
- std::is_trivially_move_assignable
- std::is_trivially_move_constructible
ms.openlocfilehash: ff6d6066d90fe5049b89586ce657e62860c12f9f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="lttypetraitsgt-functions"></a>&lt;type_traits&gt;, fonctions

||||
|-|-|-|
|[is_assignable](#is_assignable)|[is_copy_assignable](#is_copy_assignable)|[is_copy_constructible](#is_copy_constructible)|
|[is_default_constructible](#is_default_constructible)|[is_move_assignable](#is_move_assignable)|[is_move_constructible](#is_move_constructible)|
|[is_nothrow_move_assignable](#is_nothrow_move_assignable)|[is_trivially_copy_assignable](#is_trivially_copy_assignable)|[is_trivially_move_assignable](#is_trivially_move_assignable)|
|[is_trivially_move_constructible](#is_trivially_move_constructible)|

## <a name="is_assignable"></a>  is_assignable

Teste si une valeur de type `From` peut être assignée à un type `To`.

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Paramètres

Pour le type de l’objet qui reçoit l’assignation.

À partir du type de l’objet qui fournit la valeur.

### <a name="remarks"></a>Notes

L’expression non évaluée `declval<To>() = declval<From>()` doit être bien formée. `From` et `To` doivent tous deux être des types complets, `void` ou des tableaux de limite inconnue.

## <a name="is_copy_assignable"></a>  is_copy_assignable

Teste si le type peut être copié lors de l'assignation.

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>Paramètres

`Ty` Type à interroger.

### <a name="remarks"></a>Notes

Une instance du prédicat de type a la valeur true si le type `Ty` est une classe qui a un opérateur d'assignation de copie. Sinon, sa valeur est false. Équivaut à is_assignable\<Ty&, const Ty&>.

## <a name="is_copy_constructible"></a>  is_copy_constructible

Teste si le type a un constructeur de copie.

```cpp
template <class Ty>
struct is_copy_constructible;
```

### <a name="parameters"></a>Paramètres

`Ty` Type à interroger.

### <a name="remarks"></a>Notes

Une instance du prédicat de type a la valeur true si le type `Ty` est une classe qui a un constructeur de copie. Sinon, sa valeur est false.

### <a name="example"></a>Exemple

```cpp
#include <type_traits>
#include <iostream>

struct Copyable
{
    int val;
};

struct NotCopyable
{
   NotCopyable(const NotCopyable&) = delete;
   int val;

};

int main()
{
    std::cout << "is_copy_constructible<Copyable> == " << std::boolalpha
        << std::is_copy_constructible<Copyable>::value << std::endl;
    std::cout << "is_copy_constructible<NotCopyable> == " << std::boolalpha
        << std::is_copy_constructible<NotCopyable>::value << std::endl;

    return (0);
}

```

```Output
is_copy_constructible<Copyable> == true
is_copy_constructible<NotCopyable > == false
```

## <a name="is_default_constructible"></a>  is_default_constructible

Teste si un type a un constructeur par défaut.

```cpp
template <class Ty>
struct is_default_constructible;
```

### <a name="parameters"></a>Paramètres

`T` Type à interroger.

### <a name="remarks"></a>Notes

Une instance du prédicat de type a la valeur true si le type `T` est un type de classe qui a un constructeur par défaut. Sinon, sa valeur est false. Cela est équivalent au prédicat `is_constructible<T>`. Le type `T` doit être un type complet, `void`, ou un tableau ayant des limites d’index inconnues.

### <a name="example"></a>Exemple

```cpp
#include <type_traits>
#include <iostream>

struct Simple
{
    Simple() : val(0) {}
    int val;
};

struct Simple2
{
    Simple2(int v) : val(v) {}
    int val;
};

int main()
{
    std::cout << "is_default_constructible<Simple> == " << std::boolalpha
        << std::is_default_constructible<Simple>::value << std::endl;
    std::cout << "is_default_constructible<Simple2> == " << std::boolalpha
        << std::is_default_constructible<Simple2>::value << std::endl;

    return (0);
}

```

```Output
is_default_constructible<Simple> == true
is_default_constructible<Simple2> == false
```

## <a name="is_move_assignable"></a>  is_move_assignable

Teste si le type peut être assigné par déplacement.

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Paramètres

`T` Type à interroger.

### <a name="remarks"></a>Notes

Un type est assignable par déplacement si une référence rvalue au type peut être assignée à une référence au type. Le prédicat de type équivaut à `is_assignable<T&, T&&>`. Les types assignables par déplacement incluent les types scalaires référençables et les types de classe qui ont des opérateurs d’assignation par déplacement générés par le compilateur ou définis par l’utilisateur.

## <a name="is_move_constructible"></a>  is_move_constructible

Teste si le type a un constructeur de déplacement.

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Paramètres

T le type à évaluer

### <a name="remarks"></a>Notes

Prédicat de type qui a la valeur true si le type `T` est constructible par une opération de déplacement. Ce prédicat équivaut à `is_constructible<T, T&&>`.

## <a name="is_nothrow_move_assignable"></a>  is_nothrow_move_assignable

Teste si le type a un opérateur d’assignation par déplacement **nothrow**.

```cpp
template <class Ty>
struct is_nothrow_move_assignable;
```

### <a name="parameters"></a>Paramètres

`Ty` Type à interroger.

### <a name="remarks"></a>Notes

Une instance du prédicat de type a la valeur true si le type `Ty` a un opérateur d'assignation de déplacement nothrow. Sinon, sa valeur est false.

## <a name="is_trivially_copy_assignable"></a>  is_trivially_copy_assignable

Teste si le type a un opérateur d'assignation de copie trivial.

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Paramètres

`T` Type à interroger.

### <a name="remarks"></a>Notes

Une instance du prédicat de type a la valeur true si le type `T` est une classe qui a un opérateur d'assignation de copie trivial. Sinon, sa valeur est false.

Un constructeur d’assignation d’une classe `T` est trivial s’il est fourni implicitement, si la classe `T` n’a aucune fonction virtuelle, si la classe `T` n’a aucune base virtuelle, si les classes de toutes les données membres non statiques de type classe ont des opérateurs d’assignation triviaux et si les classes de toutes les données membres non statiques de type tableau de classe ont des opérateurs d’assignation triviaux.

## <a name="is_trivially_move_assignable"></a>  is_trivially_move_assignable

Teste si le type a un opérateur d'assignation de déplacement trivial.

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Paramètres

`Ty` Type à interroger.

### <a name="remarks"></a>Notes

Une instance du prédicat de type a la valeur true si le type `Ty` est une classe qui a un opérateur d'assignation de déplacement trivial. Sinon, sa valeur est false.

Un opérateur d'assignation de déplacement pour une classe `Ty` est trivial si :

il est fourni implicitement ;

la classe `Ty` n'a aucune fonction virtuelle ;

la classe `Ty` n'a aucune base virtuelle ;

les classes de tous les membres de données non statiques de type classe possèdent des opérateurs d'assignation de déplacement triviaux ;

les classes de tous les membres de données non statiques de type tableau de classe possèdent des opérateurs d'assignation de déplacement triviaux.

## <a name="is_trivially_move_constructible"></a>  is_trivially_move_constructible

Teste si le type a un constructeur de déplacement trivial.

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Paramètres

`Ty` Type à interroger.

### <a name="remarks"></a>Notes

Une instance du prédicat de type a la valeur true si le type `Ty` est une classe qui a un constructeur de déplacement trivial. Sinon, sa valeur est false.

Un constructeur de déplacement pour une classe `Ty` est trivial si :

il est déclaré implicitement ;

ses types de paramètres sont équivalents à ceux d'une déclaration implicite ;

la classe `Ty` n'a aucune fonction virtuelle ;

la classe `Ty` n'a aucune base virtuelle ;

la classe n'a aucun membre de données non statique volatile ;

toutes les bases directes de la classe `Ty` ont des constructeurs de déplacement triviaux ;

les classes de tous les membres de données non statiques de type de classe ont des constructeurs de déplacement triviaux ;

les classes de tous les membres de données non statiques de type tableau de classe ont des constructeurs de déplacement triviaux.

## <a name="see-also"></a>Voir aussi

[<type_traits>](../standard-library/type-traits.md)<br/>
