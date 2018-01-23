---
title: Conteneurs (Modern C++) | Documents Microsoft
ms.custom: 
ms.date: 1/18/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d43570f644e9627de5a40fc5b824a17e4fd33ffc
ms.sourcegitcommit: 6f40bba1772a09ff0e3843d5f70b553e1a15ab50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/22/2018
---
# <a name="containers-modern-c"></a>Conteneurs (Modern C++)

Par défaut, utilisez [vecteur](../standard-library/vector-class.md) en tant que le conteneur par défaut séquentiel en C++. Cela est équivalent à `List<T>` dans les langages .NET.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

Utilisez [carte](../standard-library/map-class.md) (pas `unordered_map`) comme conteneur associatif par défaut. Utilisez [définir](../standard-library/set-class.md), [multimap](../standard-library/multimap-class.md), et [multiset](../standard-library/multiset-class.md) dégénérée & plusieurs cas.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

Lors de l’optimisation des performances est nécessaire, envisagez d’utiliser :

- Le [tableau](../standard-library/array-class-stl.md) lorsque l’incorporation est importante, par exemple, en tant qu’un membre de classe de type.

- Désordonnés tels que les conteneurs associatifs [unordered_map](../standard-library/unordered-map-class.md). Ces messages ont surcharge élément inférieur et une recherche constante, mais ils peuvent être plus difficile à utiliser correctement et efficacement.

- Triées **vecteur**. Pour plus d’informations, consultez [Algorithmes](../cpp/algorithms-modern-cpp.md).

N’utilisez pas les tableaux de style C. Pour plus anciennes API qui doivent pouvoir accéder aux données directement, utilisez les méthodes d’accesseur telles que `f(vec.data(), vec.size());` à la place.

Pour plus d’informations sur les conteneurs, consultez [conteneurs de bibliothèque C++ Standard](../standard-library/stl-containers.md).

## <a name="see-also"></a>Voir aussi

[Bienvenue dans C++](../cpp/welcome-back-to-cpp-modern-cpp.md)  
[Informations de référence sur le langage C++](../cpp/cpp-language-reference.md)  
[Bibliothèque C++ standard](../standard-library/cpp-standard-library-reference.md)  
