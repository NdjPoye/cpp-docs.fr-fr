---
title: "MapView::MapView (constructeur) | Microsoft Docs"
ms.custom: ""
ms.date: "01/24/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::MapView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::MapView (constructeur)"
ms.assetid: 67a3250c-b527-47ac-a103-0fd186046d71
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::MapView (constructeur)
Initialise une nouvelle instance de la classe MapView.  
  
## Syntaxe  
  
```  
explicit MapView(  
    const C& comp = C()  
    );  
  
explicit MapView(  
    const ::std::map<K, V, C>& m  
    );  
  
explicit MapView(  
    std::map<K, V, C>&& m  
    );  
  
template <typename InIt> MapView(  
    InIt first,  
    InIt last,  
    const C& comp = C()  
    );  
  
MapView(::std::initializer_list<  
    std::pair<const K, V>> il,  
    const C& comp = C()  
    );  
```  
  
#### Paramètres  
 `InIt`  
 Typename du MapView actif.  
  
 `comp`  
 Objet de fonction qui peut comparer deux valeurs d'élément comme des clés de tri pour déterminer leur ordre relatif dans le MapView.  
  
 `m`  
 Une référence ou [Lvalues et Rvalues](~/cpp/lvalues-and-rvalues-visual-cpp.md) à [map, classe](../standard-library/map-class.md) utilisée pour initialiser le MapView actif.  
  
 `first`  
 Itérateur d'entrée du premier élément d'une plage d'éléments utilisée pour initialiser le MapView actif.  
  
 `last`  
 Itérateur d'entrée du premier élément qui suit une plage d'éléments utilisée pour initialiser le MapView actif.  
  
 il  
 [std::initializer\_list\<std::pair\<K,V\>\>](../standard-library/initializer-list-class.md) dont les éléments sont insérés dans le MapView.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::MapView, classe](../cppcx/platform-collections-mapview-class.md)