---
title: forward_iterator_tag, struct | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xutility/std::forward_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2fa9e405162f0ed56866a5c8e15d894010396e1
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="forwarditeratortag-struct"></a>forward_iterator_tag, struct

Classe qui fournit un type de retour pour une fonction **iterator_category** représentant un itérateur vers l’avant.

## <a name="syntax"></a>Syntaxe

```cpp
struct forward_iterator_tag    : public input_iterator_tag {};
```

## <a name="remarks"></a>Notes

Les classes de balise de catégorie sont utilisées comme balises de compilation pour la sélection de l’algorithme. La fonction de modèle doit déterminer la catégorie la plus spécifique de son argument d’itérateur pour pouvoir utiliser l’algorithme le plus efficace au moment de la compilation. Pour chaque itérateur de type `Iterator`, `iterator_traits`< `Iterator`> **::iterator_category** doit être défini comme étant la balise de catégorie la plus spécifique qui décrit le comportement de l’itérateur.

Le type est identique à **iterator**\< **Iter**> **::iterator_category** quand **Iter** décrit un objet pouvant servir d’itérateur vers l’avant.

## <a name="example"></a>Exemple

Consultez [iterator_traits](../standard-library/iterator-traits-struct.md) ou [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) pour obtenir un exemple d’utilisation des **iterator_tag**s.

## <a name="requirements"></a>Spécifications

**En-tête :** \<iterator>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[input_iterator_tag, struct](../standard-library/input-iterator-tag-struct.md)<br/>
[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)<br/>
