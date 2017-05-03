---
title: "Map::Map (constructeur) | Microsoft Docs"
ms.custom: ""
ms.date: "01/24/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::Map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::Map (constructeur)"
ms.assetid: 4cd314eb-e3e3-4fa7-8c58-96e48d167246
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::Map (constructeur)
Initialise une nouvelle instance de la classe Map.  
  
## Syntaxe  
  
```  
explicit Map(  
   const C& comp = C()  
);  
explicit Map(  
   const StdMap& m  
);  
explicit Map(  
   StdMap&& m  
);  
template <  
   typename InIt  
>  
Map(  
   InItfirst,  
   InItlast,  
   const C& comp = C()  
);  
```  
  
#### Paramètres  
 `InIt`  
 Nom de type de l'objet Map actuel.  
  
 `comp`  
 Type qui fournit un objet de fonction qui peut comparer deux valeurs d'élément comme des clés de tri pour déterminer leur ordre relatif dans le Map.  
  
 `m`  
 Une référence ou [Lvalues et Rvalues](~/cpp/lvalues-and-rvalues-visual-cpp.md) à [map, classe](../standard-library/map-class.md) utilisée pour initialiser l'objet Map actuel.  
  
 `first`  
 Itérateur d'entrée du premier élément d'une plage d'éléments utilisée pour initialiser le Map actuel.  
  
 `last`  
 Itérateur d'entrée du premier élément qui suit une plage d'éléments utilisée pour initialiser le Map actuel.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::Map, classe](../cppcx/platform-collections-map-class.md)