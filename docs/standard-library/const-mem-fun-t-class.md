---
title: const_mem_fun_t, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xfunctional/std::const_mem_fun_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun_t class
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8189148262f0996f8082db154f161c03615da530
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="constmemfunt-class"></a>const_mem_fun_t, classe

Classe d’adaptateur qui permet à une fonction membre const qui n’accepte aucun argument d’être appelée comme objet de fonction unaire en cas d’initialisation avec un argument de référence.

## <a name="syntax"></a>Syntaxe

```cpp
template <class Result, class Type>
class const_mem_fun_t : public unary_function <Type *, Result>
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type* Pleft) const;
 };
```

### <a name="parameters"></a>Paramètres

`Pm` Un pointeur vers la fonction membre de classe **Type** pour être converti en un objet de fonction.

`Pleft` L’objet qui le `Pm` fonction membre est appelée sur.

## <a name="return-value"></a>Valeur de retour

Fonction unaire adaptable.

## <a name="remarks"></a>Notes

La classe de modèle stocke une copie de `Pm`, qui doit être un pointeur vers une fonction membre de la classe **Type**, dans un objet de membre privé. Elle définit sa fonction membre `operator()` comme retournant ( `Pleft`->\* `Pm`)() **const**.

## <a name="example"></a>Exemple

Le constructeur de `const_mem_fun_t` n’est généralement pas utilisé directement ; la fonction d’assistance `mem_fun` est utilisée pour adapter les fonctions membres. Pour obtenir un exemple d’utilisation des adaptateurs de fonction membre, consultez [mem_fun](../standard-library/functional-functions.md#mem_fun).

## <a name="requirements"></a>Spécifications

**En-tête :** \<functional>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)<br/>
