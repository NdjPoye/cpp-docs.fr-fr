---
title: iterator, struct | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xutility/std::iterator
dev_langs:
- C++
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6bf766bdcb63ae4d50006f4a2d7722238663c610
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="iterator-struct"></a>iterator, struct

Struct de base vide permettant de garantir qu’une classe d’itérateur définie par l’utilisateur fonctionne correctement avec des **iterator_trait**.

## <a name="syntax"></a>Syntaxe

```cpp
struct iterator {
   typedef Category iterator_category;
   typedef Type value_type;
   typedef Distance difference_type;
   typedef Distance distance_type;
   typedef Pointer pointer;
   typedef Reference reference;
   };
```

## <a name="remarks"></a>Notes

Le struct de modèle sert de type de base pour tous les itérateurs. Il définit les types de membres

- `iterator_category` (synonyme du paramètre du modèle `Category`).

- `value_type` (synonyme du paramètre du modèle **Type**).

- `difference_type` (synonyme du paramètre du modèle `Distance`).

- `distance_type` (synonyme du paramètre du modèle `Distance`)

- `pointer` (synonyme du paramètre du modèle `Pointer`).

- `reference` (synonyme du paramètre du modèle `Reference`).

Notez que `value_type` ne doit pas être un type de constante, même si **pointer** pointe vers un objet de **Type** const et que la référence désigne un objet de **Type** const.

## <a name="example"></a>Exemple

Pour obtenir un exemple montrant comment déclarer et utiliser les types de la classe de base iterator, consultez [iterator_traits](../standard-library/iterator-traits-struct.md).

## <a name="requirements"></a>Spécifications

**En-tête :** \<iterator>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[\<iterator>](../standard-library/iterator.md)<br/>
[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)<br/>
