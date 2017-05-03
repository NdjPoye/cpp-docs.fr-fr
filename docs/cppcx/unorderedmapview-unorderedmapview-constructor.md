---
title: "UnorderedMapView::UnorderedMapView, constructeur | Microsoft Docs"
ms.custom: ""
ms.date: "01/24/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::UnorderedMapView"
ms.assetid: 408aa6ca-dd8d-4946-a817-42a31d19f429
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::UnorderedMapView, constructeur
Initialise une nouvelle instance de la classe UnorderedMapView.  
  
## Syntaxe  
  
```cpp  
  
UnorderedMapView();  
  
explicit UnorderedMapView(size_t n);  
  
UnorderedMapView(size_t n, const H& h);  
  
UnorderedMapView(size_t n, const H& h, const P& p);  
  
explicit UnorderedMapView(  
    const std::unordered_map<K, V, H, P>& m  
    );  
explicit UnorderedMapView(  
    std::unordered_map<K, V, H, P>&& m  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h,  
    const P& p  
    );  
  
UnorderedMapView(  
    std::initializer_list<std::pair<const K, V>> il  
    );  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n  
    );  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h  
    );  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h,  
    const P& p  
    );  
```  
  
#### Paramètres  
 n  
 Nombre d'éléments pour lesquels préallouer de l'espace.  
  
 `InIt`  
 Nom de type du UnorderedMapView.  
  
 `H`  
 Objet de fonction qui peut avoir une valeur de hachage pour une clé. Correspond par défaut à [std::hash\<K\>](http://msdn.microsoft.com/fr-fr/54f67435-af9d-4217-a29d-fa4d2491a104) pour les types que `std::hash` prend en charge.  
  
 `P`  
 Type qui fournit un objet de fonction qui peut comparer deux clés pour déterminer leur égalité. Correspond par défaut à [std::equal\_to\<K\>](../standard-library/equal-to-struct.md).  
  
 `m`  
 Une référence ou [Lvalues et Rvalues](../Topic/Lvalues%20and%20Rvalues%20\(Visual%20C++\).md) à [](../standard-library/unordered-map-class.md) utilisée pour initialiser le UnorderedMapView.  
  
 `first`  
 Itérateur d'entrée du premier élément d'une plage d'éléments utilisée pour initialiser le UnorderedMapView.  
  
 `last`  
 Itérateur d'entrée du premier élément qui suit une plage d'éléments utilisée pour initialiser le UnorderedMapView.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::UnorderedMapView, classe](../cppcx/platform-collections-unorderedmapview-class.md)