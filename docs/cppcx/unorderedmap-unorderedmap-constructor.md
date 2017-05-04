---
title: "UnorderedMap::UnorderedMap, constructeur | Microsoft Docs"
ms.custom: ""
ms.date: "01/24/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::UnorderedMap"
ms.assetid: bd62e663-7f3a-43ef-ad6d-8266128c778b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::UnorderedMap, constructeur
Initialise une nouvelle instance de la classe UnorderedMap.  
  
## Syntaxe  
  
```scr  
UnorderedMap();  
  
  explicit UnorderedMap(  
      size_t n  
      );  
  
  UnorderedMap(  
      size_t n,  
      const H& h  
      );  
  
  UnorderedMap(  
      size_t n,  
      const H& h,  
      const P& p  
      );  
  
  explicit UnorderedMap(  
      const std::unordered_map<K, V, H, P>& m  
      );  
  
  explicit UnorderedMap(  
      std::unordered_map<K, V, H, P>&& m  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n,  
      const H& h  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n,  
      const H& h,  
      const P& p  
      );  
  
  UnorderedMap(std::initializer_list<  
      std::pair<const K, V>> il  
      );  
  
  UnorderedMap(::std::initializer_list<  
      std::pair<const K, V>> il,  
      size_t n  
      );  
  
  UnorderedMap(  
      ::std::initializer_list< ::std::pair<const K, V>> il,  
      size_t n,  
      const H& h  
      );  
  
  UnorderedMap(::std::initializer_list<  
      ::std::pair<const K, V>> il,  
      size_t n,  
      const H& h,  
      const P& p  
      );  
```  
  
#### Paramètres  
 `InIt`  
 Nom de type du UnorderedMap actif.  
  
 `P`  
 Objet de fonction qui peut comparer deux clés pour déterminer si elles sont égales. La valeur par défaut de ce paramètre est [std::equal\_to\<K\>](../standard-library/equal-to-struct.md).  
  
 `H`  
 Objet de fonction qui génère une valeur de hachage pour les clés. La valeur par défaut de ce paramètre est [hash, classe](../Topic/hash%20Class%201.md) pour les types de clé que cette classe prend en charge.  
  
 `m`  
 Référence ou [Lvalues et Rvalues](~/cpp/lvalues-and-rvalues-visual-cpp.md) d'un [std::unordered\_map](../standard-library/unordered-map-class.md) utilisé pour initialiser le UnorderedMap actif.  
  
 il  
 [std::initializer\_list](../standard-library/initializer-list-class.md) des objets [std::pair](../standard-library/pair-structure.md)qui seront utilisés pour initialiser le mappage.  
  
 `first`  
 Itérateur d'entrée du premier élément d'une plage d'éléments utilisée pour initialiser le UnorderedMap actif.  
  
 `last`  
 Itérateur d'entrée du premier élément qui suit une plage d'éléments utilisée pour initialiser le UnorderedMap actif.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections \(espace de noms\)](../cppcx/platform-collections-namespace.md)   
 [Collections](../cppcx/collections-c-cx.md)