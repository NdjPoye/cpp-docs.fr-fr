---
title: '&lt;exception&gt;, typedefs | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- exception/std::exception_ptr
- exception/std::terminate_handler
- exception/std::unexpected_handler
ms.assetid: 2a338480-35e2-46f7-b223-52d4e84a5768
ms.openlocfilehash: 68f95407fe22c7e8b70426e555f46eb0a4c80338
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="ltexceptiongt-typedefs"></a>&lt;exception&gt;, typedefs

||||
|-|-|-|
|[exception_ptr](#exception_ptr)|[terminate_handler](#terminate_handler)|[unexpected_handler](#unexpected_handler)|

## <a name="exception_ptr"></a>  exception_ptr

Type qui décrit un pointeur vers une exception.

```cpp
typedef unspecified exception_ptr;
```

### <a name="remarks"></a>Notes

Une classe interne non spécifiée utilisée pour implémenter le type `exception_ptr`.

Utilisez un objet `exception_ptr` pour référencer l'exception actuelle ou une instance d'une exception spécifiée par l'utilisateur. Dans l’implémentation Microsoft, une exception est représentée par une structure [EXCEPTION_RECORD](http://msdn.microsoft.com/library/windows/desktop/aa363082). Chaque objet `exception_ptr` inclut un champ de référence d'exception qui pointe vers une copie de la structure `EXCEPTION_RECORD` qui représente l'exception.

Lorsque vous déclarez une variable `exception_ptr`, la variable n'est associée à aucune exception. Autrement dit, son champ de référence d'exception est NULL. Ce type d’objet `exception_ptr` est appelé *exception_ptr null*.

Utilisez la fonction `current_exception` ou `make_exception_ptr` pour assigner une exception à un objet `exception_ptr`. Lorsque vous assignez une exception à une variable `exception_ptr`, le champ de référence de l'exception de la variable pointe vers une copie de l'exception. Si la mémoire est insuffisante pour copier l’exception, le champ de référence d’exception pointe vers une copie d’une exception [std::bad_alloc](../standard-library/bad-alloc-class.md). Si la fonction `current_exception` ou `make_exception_ptr` ne peut pas copier l’exception pour une autre raison, elle appelle la fonction CRT **terminate** pour quitter le processus actuel.

En dépit de son nom, un objet `exception_ptr` n'est pas lui-même un pointeur. Il ne respecte pas la sémantique des pointeurs et ne peut pas être utilisé avec les accès des membres pointeurs (`->`) ou des opérateurs d’indirection (*). L'objet `exception_ptr` n'a aucune donnée membre ou fonction membre publique.

**Comparaisons :**

Vous pouvez utiliser les opérateurs Égal à (`==`) et Non égal à (`!=`) pour comparer deux objets `exception_ptr`. Les opérateurs ne comparent pas la valeur binaire (modèle binaire) des structures `EXCEPTION_RECORD` qui représentent les exceptions. À la place, les opérateurs comparent les adresses dans le domaine de référence d'exception des objets `exception_ptr`. Par conséquent, une exception `exception_ptr` null et la valeur NULL sont considérées comme égales.

## <a name="terminate_handler"></a>  terminate_handler

Type qui décrit un pointeur vers une fonction appropriée pour une utilisation en tant que `terminate_handler`.

```cpp
typedef void (*terminate_handler)();
```

### <a name="remarks"></a>Notes

Le type décrit un pointeur vers une fonction appropriée devant être utilisée en tant que gestionnaire d'arrêt.

### <a name="example"></a>Exemple

Consultez [set_terminate](../standard-library/exception-functions.md#set_terminate) pour obtenir un exemple d’utilisation de `terminate_handler`.

## <a name="unexpected_handler"></a>  unexpected_handler

Le type décrit un pointeur vers une fonction pouvant être utilisée comme `unexpected_handler`.

```cpp
typedef void (*unexpected_handler)();
```

### <a name="example"></a>Exemple

Consultez [set_unexpected](../standard-library/exception-functions.md#set_unexpected) pour obtenir un exemple d’utilisation de `unexpected_handler`.

## <a name="see-also"></a>Voir aussi

[\<exception>](../standard-library/exception.md)<br/>
