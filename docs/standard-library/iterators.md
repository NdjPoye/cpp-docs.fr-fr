---
title: Itérateurs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- iterator conventions
- C++ Standard Library, iterator conventions
ms.assetid: 2f746be7-b37d-4bfc-bf05-be4336ca982f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1c6b7ef094715e052bdea023bcff0437492325c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="iterators"></a>Iterators

Un itérateur est un objet qui peut itérer sur les éléments dans un conteneur de bibliothèque standard C++ et fournir un accès à des éléments spécifiques. Les conteneurs de bibliothèque standard C++ fournissent tous des itérateurs permettant aux algorithmes d’accéder à leurs éléments de façon standard, sans avoir à se préoccuper du type de conteneur où les éléments sont stockés.

Vous pouvez utiliser des itérateurs explicitement en utilisant des membres et des fonctions globales, comme begin() et end(), et des opérateurs, comme ++ et -- pour avancer ou pour reculer. Vous pouvez également utiliser des itérateurs implicitement avec une boucle for basée sur un intervalle ou (pour certains types d'itérateurs) avec l'opérateur d'indice [].

Dans la bibliothèque standard C++, le début d’une séquence ou d’une plage est le premier élément. La fin d'une séquence ou d'une plage est toujours définie comme étant à l'emplacement suivant le dernier élément. Les fonctions globales begin et end retournent des itérateurs à un conteneur spécifié. La boucle d'itérateur explicite standard sur tous les éléments d'un conteneur ressemble à ceci :

```cpp
vector<int> vec{ 0,1,2,3,4 };
for (auto it = begin(vec);

it != end(vec);

it++)
{  // Access element using dereference operator
    cout <<*it <<" ";
}
```

La même chose peut être accomplie plus simplement avec une boucle for basée sur un intervalle :

```cpp
for (auto num : vec)
 {  // no deference operator
    cout <<num <<" ";
 }
```

Il existe cinq catégories d'itérateurs. Par ordre de puissance croissante, les catégories sont :

- **Sortie**. Un itérateur de sortie `X` peut itérer vers l'avant sur une séquence avec l'opérateur ++, et il ne peut écrire un élément qu'une seule fois avec l'opérateur *.

- **Entrée**. Un itérateur d'entrée `X` peut itérer vers l'avant sur une séquence avec l'opérateur ++, et il peut lire un élément plusieurs fois avec l'opérateur *. Vous pouvez comparer des itérateurs d'entrée à l'aide des opérateurs ++ et !=. Une fois que vous incrémentez une copie d'un itérateur d'entrée, aucune des autres copies ne peut être comparée, déréférencée ou incrémentée de façon fiable par la suite.

- **Vers l’avant**. Un itérateur vers l'avant `X` peut itérer vers l'avant sur une séquence avec l'opérateur ++ et peut lire n'importe quel élément ou écrire des éléments autres que const un nombre quelconque de fois avec l'opérateur *. Vous pouvez accéder aux membres de l'élément avec l'opérateur -> et comparer les itérateurs vers l'avant avec les opérateurs == et !=. Vous pouvez effectuer plusieurs copies d'un itérateur vers l'avant, chacune d'elles pouvant être déréférencée et incrémentée indépendamment. Un itérateur vers l'avant qui est initialisé sans référence à aucun conteneur est appelé un itérateur vers l'avant null. La comparaison d'itérateurs vers l'avant null donne toujours une égalité.

- Bidirectionnel. Un itérateur bidirectionnel `X` peut remplacer un itérateur vers l'avant. Toutefois, vous pouvez également décrémenter un itérateur bidirectionnel, comme dans --`X`, `X`-- ou (`V` = *`X`--). Vous pouvez accéder aux membres de l'élément et comparer des itérateurs bidirectionnels de la même façon que pour des itérateurs vers l'avant.

- **Accès aléatoire**. Un itérateur à accès aléatoire `X` peut remplacer un itérateur bidirectionnel. Avec un itérateur à accès aléatoire, vous pouvez utiliser l'opérateur d'indice [] pour accéder aux éléments. Vous pouvez utiliser les opérateurs +, -, += et -= pour avancer ou reculer d'un nombre spécifié d'éléments et pour calculer la distance entre des itérateurs. Vous pouvez comparer des itérateurs bidirectionnels avec ==, !=, \<, >, \<= et >=.

Tous les itérateurs peuvent être affectés ou copiés. Ils sont censés être des objets légers et sont souvent passés et retournés par valeur, et non par référence. Notez également qu'aucune des opérations décrites précédemment ne peut lever une exception lorsqu'elle est effectuée sur un itérateur valide.

La hiérarchie des catégories d'itérateur peut être résumée en indiquant trois séquences. Pour l'accès en écriture seule à une séquence, vous pouvez utiliser l'une des catégories suivantes :

> itérateur de sortie<br/>
> -> itérateur vers l’avant<br/>
> -> itérateur bidirectionnel.<br/>
> -> itérateur à accès aléatoire<br/>

La flèche droite signifie "peut être remplacé par". Tout algorithme qui appelle un itérateur de sortie doit fonctionner correctement avec un itérateur vers l’avant, par exemple, mais *pas* dans l’autre sens.

Pour l'accès en lecture seule à une séquence, vous pouvez utiliser l'une des catégories suivantes :

> itérateur d’entrée<br/>
> -> itérateur vers l’avant<br/>
> -> itérateur bidirectionnel.<br/>
> -> itérateur à accès aléatoire<br/>

Un itérateur d'entrée est le plus faible de toutes les catégories, dans ce cas.

Enfin, pour l'accès en lecture/écriture à une séquence, vous pouvez utiliser l'une des catégories suivantes :

> itérateur vers l’avant<br/>
> -> itérateur bidirectionnel.<br/>
> -> itérateur à accès aléatoire<br/>

Un pointeur d'objet peut toujours servir d'itérateur à accès aléatoire, il peut donc être utilisé comme catégorie d'itérateur s'il prend en charge l'accès approprié en lecture et en écriture à la séquence qu'il désigne.

Un itérateur `Iterator` autre qu'un pointeur d'objet doit également définir les types de membres requis par la spécialisation `iterator_traits<Iterator>`. Notez que ces exigences peuvent être remplies en dérivant `Iterator` de la classe de base publique [iterator](../standard-library/iterator-struct.md).

Il est important de comprendre les promesses et les limites de chaque catégorie d’itérateur pour voir comment les itérateurs sont utilisés par les conteneurs et les algorithmes dans la bibliothèque standard C++.

> [!NOTE]
> Vous pouvez éviter d'utiliser des itérateurs explicitement avec des boucles for basées sur un intervalle. Pour plus d’informations, consultez [plage instruction for basée](../cpp/range-based-for-statement-cpp.md).

Visual C++ offre maintenant des itérateurs vérifiés et des itérateurs de débogage pour garantir que vous ne remplaciez pas les limites de votre conteneur. Pour plus d’informations, consultez [itérateurs vérifiés](../standard-library/checked-iterators.md) et [Itérateurs de débogage, prise en charge](../standard-library/debug-iterator-support.md).

## <a name="see-also"></a>Voir aussi

[Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)<br/>
[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
