---
title: shared_ptr, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- memory/std::shared_ptr
- memory/std::shared_ptr::element_type
- memory/std::shared_ptr::get
- memory/std::shared_ptr::owner_before
- memory/std::shared_ptr::reset
- memory/std::shared_ptr::swap
- memory/std::shared_ptr::unique
- memory/std::shared_ptr::use_count
- memory/std::shared_ptr::operator boolean-type
- memory/std::shared_ptr::operator*
- memory/std::shared_ptr::operator=
- memory/std::shared_ptr::operator->
dev_langs:
- C++
helpviewer_keywords:
- std::shared_ptr [C++]
- std::shared_ptr [C++], element_type
- std::shared_ptr [C++], get
- std::shared_ptr [C++], owner_before
- std::shared_ptr [C++], reset
- std::shared_ptr [C++], swap
- std::shared_ptr [C++], unique
- std::shared_ptr [C++], use_count
- std::shared_ptr [C++], element_type
- std::shared_ptr [C++], get
- std::shared_ptr [C++], owner_before
- std::shared_ptr [C++], reset
- std::shared_ptr [C++], swap
- std::shared_ptr [C++], unique
- std::shared_ptr [C++], use_count
ms.assetid: 1469fc51-c658-43f1-886c-f4530dd84860
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eff0c41993a450e74b468b747776368bae6ad848
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="sharedptr-class"></a>shared_ptr, classe

Encapsule un pointeur intelligent contenant des références autour d'un objet alloué dynamiquement.

## <a name="syntax"></a>Syntaxe

```cpp
template <class T>
class shared_ptr;
```

## <a name="remarks"></a>Notes

La classe shared_ptr décrit un objet qui utilise le décompte de références pour gérer les ressources. Un objet `shared_ptr` contient en fait un pointeur vers la ressource qu'il possède ou contient un pointeur null. Une ressource peut être détenue par plusieurs objets `shared_ptr`. Quand le dernier objet `shared_ptr` qui possède une ressource particulière est détruit, la ressource est libérée.

Un `shared_ptr` cesse de posséder une ressource quand il est réaffecté ou réinitialisé.

L'argument de modèle `T` peut être un type incomplet, sauf comme mentionné pour certaines fonctions membres.

Quand un objet `shared_ptr<T>` est construit à partir d'un pointeur de ressource de type `G*` ou à partir d'un `shared_ptr<G>`, le type de pointeur `G*` doit être convertible en `T*`. Si ce n'est pas le cas, le code n'est pas compilé. Par exemple :

```cpp
#include <memory>
using namespace std;

class F {};
class G : public F {};

shared_ptr<G> sp0(new G);   // okay, template parameter G and argument G*
shared_ptr<G> sp1(sp0);     // okay, template parameter G and argument shared_ptr<G>
shared_ptr<F> sp2(new G);   // okay, G* convertible to F*
shared_ptr<F> sp3(sp0);     // okay, template parameter F and argument shared_ptr<G>
shared_ptr<F> sp4(sp2);     // okay, template parameter F and argument shared_ptr<F>
shared_ptr<int> sp5(new G); // error, G* not convertible to int*
shared_ptr<int> sp6(sp2);   // error, template parameter int and argument shared_ptr<F>
```

Un objet `shared_ptr` possède une ressource :

- s'il a été construit avec un pointeur vers cette ressource ;

- s'il a été construit à partir d'un objet `shared_ptr` qui possède cette ressource ;

- s’il a été construit à partir d’un objet de [classe weak_ptr](../standard-library/weak-ptr-class.md) qui pointe vers cette ressource ; ou

- si la propriété de cette ressource lui a été assignée en utilisant [shared_ptr::operator=](#op_eq) ou en appelant la fonction membre [shared_ptr::resetshared_ptr::reset](#reset).

Les objets `shared_ptr` qui sont propriétaires d'une ressource partagent un bloc de contrôle. Le bloc de contrôle contient :

- le nombre d'objets `shared_ptr` qui sont propriétaires de la ressource ;

- le nombre d'objets `weak_ptr` qui pointent vers la ressource ;

- le suppresseur de cette ressource, le cas échéant ;

- l'allocateur personnalisé pour le bloc de contrôle, le cas échéant.

Un objet `shared_ptr` qui est initialisé à l'aide d'un pointeur null a un bloc de contrôle et n'est pas vide. Une fois qu'un objet `shared_ptr` a libéré une ressource, il n'en est plus propriétaire. Une fois qu'un objet `weak_ptr` a libéré une ressource, il ne pointe plus vers cette ressource.

Quand le nombre d'objets `shared_ptr` propriétaires d'une ressource devient égal à zéro, la ressource est libérée, soit en étant supprimée, soit en passant son adresse à un suppresseur, selon la façon dont la propriété de la ressource a été créée initialement. Quand le nombre d'objets `shared_ptr` propriétaires d'une ressource est égal à zéro et que le nombre d'objets `weak_ptr` qui pointent vers cette ressource est égal à zéro, le bloc de contrôle est libéré, à l'aide de l'allocateur personnalisé du bloc de contrôle s'il en a un.

Un objet `shared_ptr` vide ne possède pas de ressource et n'a aucun bloc de contrôle.

Un suppresseur est un objet de fonction qui a une fonction membre `operator()`. Son type doit être constructible par copie et son constructeur de copie et son destructeur ne doivent pas lever d'exceptions. Il accepte un paramètre, l'objet à supprimer.

Certaines fonctions acceptent une liste d'arguments qui définit les propriétés de l'objet `shared_ptr<T>` ou `weak_ptr<T>` résultant. Vous pouvez spécifier une telle liste d'arguments de plusieurs façons :

aucun argument : l'objet résultant est un objet `shared_ptr` vide ou un objet `weak_ptr` vide.

`ptr` : un pointeur de type `Other*` vers la ressource à gérer. `T` doit être un type complet. Si la fonction échoue (car le bloc de contrôle ne peut pas être alloué), elle évalue l'expression `delete ptr`.

`ptr, dtor` : un pointeur de type `Other*` vers la ressource à gérer et un suppresseur pour cette ressource. Si la fonction échoue (car le bloc de contrôle ne peut pas être alloué), elle appelle `dtor(ptr)`, qui doit être défini correctement.

`ptr, dtor, alloc` : un pointeur de type `Other*` vers la ressource à gérer, un suppresseur pour cette ressource et un allocateur pour gérer tout stockage qui doit être alloué et libéré. Si la fonction échoue (car le bloc de contrôle ne peut pas être alloué), elle appelle `dtor(ptr)`, qui doit être défini correctement.

`sp` : un objet `shared_ptr<Other>` propriétaire de la ressource à gérer.

`wp` : un objet `weak_ptr<Other>` qui pointe vers la ressource à gérer.

`ap` : un objet `auto_ptr<Other>` qui contient un pointeur vers la ressource à gérer. Si la fonction réussit, elle appelle `ap.release()` ; sinon, elle laisse `ap` inchangé.

Dans tous les cas, le type de pointeur `Other*` doit être convertible en `T*`.

## <a name="thread-safety"></a>Sécurité des threads

Plusieurs threads peuvent lire et écrire différents objets `shared_ptr` simultanément, même quand les objets sont des copies qui partagent la propriété.

## <a name="members"></a>Membres

### <a name="constructors"></a>Constructeurs

|Constructeur|Description|
|-|-|
|[shared_ptr](#shared_ptr)|Construit un objet `shared_ptr`.|
|[shared_ptr::~shared_ptr](#dtorshared_ptr)|Détruit un `shared_ptr`.|

### <a name="types"></a>Types

|Nom de type|Description|
|-|-|
|[element_type](#element_type)|Type d’un élément.|

### <a name="functions"></a>Fonctions

|Fonction|Description|
|-|-|
|[get](#get)|Obtient l'adresse de la ressource détenue.|
|[owner_before](#owner_before)|Retourne true si ce `shared_ptr` est classé avant le pointeur fourni (ou est inférieur à celui-ci).|
|[reset](#reset)|Remplacer la ressource détenue.|
|[swap](#swap)|Échange deux objets `shared_ptr`.|
|[unique](#unique)|Teste si la ressource détenue est unique.|
|[use_count](#use_count)|Compte le nombre de propriétaires de ressources.|

### <a name="operators"></a>Opérateurs

|Opérateur|Description|
|-|-|
|[shared_ptr::operator bool](#op_bool)|Teste si une ressource détenue existe.|
|[shared_ptr::operator*](#op_star)|Obtient la valeur désignée.|
|[shared_ptr::operator=](#op_eq)|Remplace la ressource détenue.|
|[shared_ptr::operator-&gt;](#op_arrow)|Obtient un pointeur vers la valeur désignée.|

## <a name="requirements"></a>Spécifications

**En-tête :** \<memory>

**Espace de noms :** std

## <a name="element_type"></a>  shared_ptr::element_type

Type d’un élément.

```cpp
typedef T element_type;
```

### <a name="remarks"></a>Notes

Le type est un synonyme du paramètre de modèle `T`.

### <a name="example"></a>Exemple

```cpp
// std__memory__shared_ptr_element_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));
    std::shared_ptr<int>::element_type val = *sp0;

    std::cout << "*sp0 == " << val << std::endl;

    return (0);
}

```

```Output
*sp0 == 5
```

## <a name="get"></a>  shared_ptr::get

Obtient l'adresse de la ressource détenue.

```cpp
T *get() const;
```

### <a name="remarks"></a>Notes

La fonction membre retourne l’adresse de la ressource détenue. Elle retourne la valeur 0 si l’objet ne possède pas de ressource.

### <a name="example"></a>Exemple

```cpp
// std__memory__shared_ptr_get.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0;
    std::shared_ptr<int> sp1(new int(5));

    std::cout << "sp0.get() == 0 == " << std::boolalpha
        << (sp0.get() == 0) << std::endl;
    std::cout << "*sp1.get() == " << *sp1.get() << std::endl;

    return (0);
}

```

```Output
sp0.get() == 0 == true
*sp1.get() == 5
```

## <a name="op_bool"></a>  shared_ptr::operator bool

Teste si une ressource détenue existe.

```cpp
explicit operator bool() const noexcept;
```

### <a name="remarks"></a>Notes

L’opérateur retourne une valeur de `true` lorsque `get() != nullptr`, sinon `false`.

### <a name="example"></a>Exemple

```cpp
// std__memory__shared_ptr_operator_bool.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0;
    std::shared_ptr<int> sp1(new int(5));

    std::cout << "(bool)sp0 == " << std::boolalpha
        << (bool)sp0 << std::endl;
    std::cout << "(bool)sp1 == " << std::boolalpha
        << (bool)sp1 << std::endl;

    return (0);
}

```

```Output
(bool)sp0 == false
(bool)sp1 == true
```

## <a name="op_star"></a>  shared_ptr::operator*

Obtient la valeur désignée.

```cpp
T& operator*() const;
```

### <a name="remarks"></a>Notes

L’opérateur d’indirection retourne `*get()`. Par conséquent, le pointeur stocké ne doit pas être Null.

### <a name="example"></a>Exemple

```cpp
// std__memory__shared_ptr_operator_st.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));

    std::cout << "*sp0 == " << *sp0 << std::endl;

    return (0);
}

```

```Output
*sp0 == 5
```

## <a name="op_eq"></a>  shared_ptr::operator=

Remplace la ressource détenue.

```cpp
shared_ptr& operator=(const shared_ptr& sp);

template <class Other>
shared_ptr& operator=(const shared_ptr<Other>& sp);

template <class Other>
shared_ptr& operator=(auto_ptr<Other>& ap);

template <class Other>
shared_ptr& operator=(auto_ptr<Other>& ap);

template <class Other>
shared_ptr& operator=(auto_ptr<Other>&& ap);

template <class Other, class Deletor>
shared_ptr& operator=(unique_ptr<Other, Deletor>&& ap);
```

### <a name="parameters"></a>Paramètres

`sp` Le pointeur partagé à copier.

`ap` Pointeur automatique à copier.

### <a name="remarks"></a>Notes

Tous les opérateurs décrémentent le nombre de références pour la ressource actuellement détenue par `*this` et assignent la propriété de la ressource nommée par la séquence d’opérandes à `*this`. Si le nombre de références atteint zéro, la ressource est libérée. Si un opérateur échoue, il laisse `*this` inchangé.

### <a name="example"></a>Exemple

```cpp
// std__memory__shared_ptr_operator_as.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0;
    std::shared_ptr<int> sp1(new int(5));
    std::auto_ptr<int> ap(new int(10));

    sp0 = sp1;
    std::cout << "*sp0 == " << *sp0 << std::endl;

    sp0 = ap;
    std::cout << "*sp0 == " << *sp0 << std::endl;

    return (0);
}

```

```Output
*sp0 == 5
*sp0 == 10
```

## <a name="op_arrow"></a>  shared_ptr::operator-&gt;

Obtient un pointeur vers la valeur désignée.

```cpp
T * operator->() const;
```

### <a name="remarks"></a>Notes

L’opérateur de sélection retourne `get()` de sorte que l’expression `sp->member` se comporte comme `(sp.get())->member`, où `sp` est un objet de la classe `shared_ptr<T>`. Le pointeur stocké ne doit donc pas être Null, et `T` doit être une classe, une structure ou une union avec un membre `member`.

### <a name="example"></a>Exemple

```cpp
// std__memory__shared_ptr_operator_ar.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

typedef std::pair<int, int> Mypair;
int main()
{
    std::shared_ptr<Mypair> sp0(new Mypair(1, 2));

    std::cout << "sp0->first == " << sp0->first << std::endl;
    std::cout << "sp0->second == " << sp0->second << std::endl;

    return (0);
}

```

```Output
sp0->first == 1
sp0->second == 2
```

## <a name="owner_before"></a>  shared_ptr::owner_before

Retourne true si ce `shared_ptr` est classé avant le pointeur fourni (ou est inférieur à celui-ci).

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr);

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr);
```

### <a name="parameters"></a>Paramètres

`ptr` Un `lvalue` référence à un `shared_ptr` ou `weak_ptr`.

### <a name="remarks"></a>Notes

La fonction membre de modèle retourne true si `*this` est `ordered before` `ptr`.

## <a name="reset"></a>  shared_ptr::reset

Remplacer la ressource détenue.

```cpp
void reset();

template <class Other>
void reset(Other *ptr;);

template <class Other, class D>
void reset(Other *ptr, D dtor);

template <class Other, class D, class A>
void reset(Other *ptr, D dtor, A alloc);
```

### <a name="parameters"></a>Paramètres

`Other` Type contrôlé par le pointeur d’argument.

`D` Le type de la suppression.

`ptr` Le pointeur à copier.

`dtor` La suppression à copier.

`A` Le type de l’allocateur.

`alloc` L’allocateur à copier.

### <a name="remarks"></a>Notes

Tous les opérateurs décrémentent le nombre de références pour la ressource actuellement détenue par `*this` et assignent la propriété de la ressource nommée par la séquence d’opérandes à `*this`. Si le nombre de références atteint zéro, la ressource est libérée. Si un opérateur échoue, il laisse `*this` inchangé.

### <a name="example"></a>Exemple

```cpp
// std__memory__shared_ptr_reset.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp(new int(5));

    std::cout << "*sp == " << std::boolalpha
        << *sp << std::endl;

    sp.reset();
    std::cout << "(bool)sp == " << std::boolalpha
        << (bool)sp << std::endl;

    sp.reset(new int(10));
    std::cout << "*sp == " << std::boolalpha
        << *sp << std::endl;

    sp.reset(new int(15), deleter());
    std::cout << "*sp == " << std::boolalpha
        << *sp << std::endl;

    return (0);
}

```

```Output
*sp == 5
(bool)sp == false
*sp == 10
*sp == 15
```

## <a name="shared_ptr"></a>  shared_ptr::shared_ptr

Construit un objet `shared_ptr`.

```cpp
shared_ptr();

shared_ptr(nullptr_t);

shared_ptr(const shared_ptr& sp);

shared_ptr(shared_ptr&& sp);

template <class Other>
explicit shared_ptr(Other* ptr);

template <class Other, class D>
shared_ptr(Other* ptr, D dtor);

template <class D>
shared_ptr(nullptr_t ptr, D dtor);

template <class Other, class D, class A>
shared_ptr(Other* ptr, D dtor, A  alloc);

template <class D, class A>
shared_ptr(nullptr_t ptr, D dtor, A alloc);

template <class Other>
shared_ptr(const shared_ptr<Other>& sp);

template <class Other>
shared_ptr(const weak_ptr<Other>& wp);

template <class &>
shared_ptr(std::auto_ptr<Other>& ap);

template <class &>
shared_ptr(std::auto_ptr<Other>&& ap);

template <class Other, class D>
shared_ptr(unique_ptr<Other, D>&& up);

template <class Other>
shared_ptr(const shared_ptr<Other>& sp, T* ptr);

template <class Other, class D>
shared_ptr(const unique_ptr<Other, D>& up) = delete;
```

### <a name="parameters"></a>Paramètres

`Other` Type contrôlé par le pointeur d’argument.

`ptr` Le pointeur à copier.

`D` Le type de la suppression.

`A` Le type de l’allocateur.

`dtor` La suppression.

`ator` L’allocateur.

`sp` Le pointeur intelligent à copier.

`wp` Le pointeur faible.

`ap` Pointeur automatique à copier.

### <a name="remarks"></a>Notes

Chaque constructeur construit un objet qui possède la ressource nommée par la séquence d’opérandes. Le constructeur `shared_ptr(const weak_ptr<Other>& wp)` lève un objet exception de [classe bad_weak_ptr](../standard-library/bad-weak-ptr-class.md) si `wp.expired()`.

### <a name="example"></a>Exemple

```cpp
// std__memory__shared_ptr_construct.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp0;
    std::cout << "(bool)sp0 == " << std::boolalpha
        << (bool)sp0 << std::endl;

    std::shared_ptr<int> sp1(new int(5));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    std::shared_ptr<int> sp2(new int(10), deleter());
    std::cout << "*sp2 == " << *sp2 << std::endl;

    std::shared_ptr<int> sp3(sp2);
    std::cout << "*sp3 == " << *sp3 << std::endl;

    std::weak_ptr<int> wp(sp3);
    std::shared_ptr<int> sp4(wp);
    std::cout << "*sp4 == " << *sp4 << std::endl;

    std::auto_ptr<int> ap(new int(15));
    std::shared_ptr<int> sp5(ap);
    std::cout << "*sp5 == " << *sp5 << std::endl;

    return (0);
}

```

```Output
(bool)sp0 == false
*sp1 == 5
*sp2 == 10
*sp3 == 10
*sp4 == 10
*sp5 == 15
```

## <a name="dtorshared_ptr"></a>  shared_ptr::~shared_ptr

Détruit un `shared_ptr`.

```cpp
~shared_ptr();
```

### <a name="remarks"></a>Notes

Le destructeur décrémente le nombre de références pour la ressource actuellement détenue par `*this`. Si le nombre de références atteint zéro, la ressource est libérée.

### <a name="example"></a>Exemple

```cpp
// std__memory__shared_ptr_destroy.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << "use count == " << sp1.use_count() << std::endl;

    {
        std::shared_ptr<int> sp2(sp1);
        std::cout << "*sp2 == " << *sp2 << std::endl;
        std::cout << "use count == " << sp1.use_count() << std::endl;
    }

    // check use count after sp2 is destroyed
    std::cout << "use count == " << sp1.use_count() << std::endl;

    return (0);
}

```

```Output
*sp1 == 5
use count == 1
*sp2 == 5
use count == 2
use count == 1
```

## <a name="swap"></a>  shared_ptr::swap

Échange deux objets `shared_ptr`.

```cpp
void swap(shared_ptr& sp);
```

### <a name="parameters"></a>Paramètres

`sp` Le pointeur partagé à échanger.

### <a name="remarks"></a>Notes

La fonction membre laisse la ressource détenue à l’origine par `*this` devenir la propriété de `sp`, et la ressource détenue à l’origine par `sp` devenir la propriété de `*this`. La fonction ne change pas le nombre de références pour les deux ressources, et ne lève pas d’exception.

### <a name="example"></a>Exemple

```cpp
// std__memory__shared_ptr_swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::shared_ptr<int> sp2(new int(10));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    sp1.swap(sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;

    swap(sp1, sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << std::endl;

    std::weak_ptr<int> wp1(sp1);
    std::weak_ptr<int> wp2(sp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    wp1.swap(wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    swap(wp1, wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    return (0);
}

```

```Output
*sp1 == 5
*sp1 == 10
*sp1 == 5

*wp1 == 5
*wp1 == 10
*wp1 == 5
```

## <a name="unique"></a>  shared_ptr::unique

Teste si la ressource détenue est unique.

```cpp
bool unique() const;
```

### <a name="remarks"></a>Notes

La fonction membre retourne `true` si aucun autre objet `shared_ptr` détient la ressource qui appartient à `*this`. Sinon, elle retourne `false`.

### <a name="example"></a>Exemple

```cpp
// std__memory__shared_ptr_unique.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::cout << "sp1.unique() == " << std::boolalpha
        << sp1.unique() << std::endl;

    std::shared_ptr<int> sp2(sp1);
    std::cout << "sp1.unique() == " << std::boolalpha
        << sp1.unique() << std::endl;

    return (0);
}

```

```Output
sp1.unique() == true
sp1.unique() == false
```

## <a name="use_count"></a>  shared_ptr::use_count

Compte le nombre de propriétaires de ressources.

```cpp
long use_count() const;
```

### <a name="remarks"></a>Notes

La fonction membre retourne le nombre d’objets `shared_ptr` qui détiennent la ressource appartenant à `*this`.

### <a name="example"></a>Exemple

```cpp
// std__memory__shared_ptr_use_count.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::cout << "sp1.use_count() == "
        << sp1.use_count() << std::endl;

    std::shared_ptr<int> sp2(sp1);
    std::cout << "sp1.use_count() == "
        << sp1.use_count() << std::endl;

    return (0);
}

```

```Output
sp1.use_count() == 1
sp1.use_count() == 2
```

## <a name="see-also"></a>Voir aussi

[weak_ptr, classe](../standard-library/weak-ptr-class.md)<br/>
[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
