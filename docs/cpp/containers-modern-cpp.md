---
title: Conteneurs (Modern C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 6e10b758-e928-4827-9c3f-86cafe54bf5b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4fc8bbc3a983e6fa50e4ae5e8590e1f1de37f02f
ms.sourcegitcommit: ff9bf140b6874bc08718674c07312ecb5f996463
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2018
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
  
1.  Le [tableau](../standard-library/array-class-stl.md) lorsque l’incorporation est importante, par exemple, en tant qu’un membre de classe de type.  
  
2.  Désordonnés tels que les conteneurs associatifs [unordered_map](../standard-library/unordered-map-class.md). Ces messages ont surcharge élément inférieur et une recherche constante, mais ils peuvent être plus difficile à utiliser correctement et efficacement.  
  
3.  Triées `vector`. Pour plus d’informations, consultez [Algorithmes](../cpp/algorithms-modern-cpp.md).  
  
N’utilisez pas les tableaux de style C. Pour plus anciennes API qui doivent pouvoir accéder aux données directement, utilisez les méthodes d’accesseur telles que `f(vec.data(), vec.size());` à la place.  
  
Pour plus d’informations sur les conteneurs, consultez [conteneurs de bibliothèque C++ Standard](../standard-library/stl-containers.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Bienvenue dans C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C++](../cpp/cpp-language-reference.md)   
 [Bibliothèque C++ standard](../standard-library/cpp-standard-library-reference.md)
