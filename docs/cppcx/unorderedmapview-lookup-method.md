---
title: "UnorderedMapView::Lookup, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::Lookup"
ms.assetid: 22f61824-ba8c-4b8c-9077-7577c41a6742
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::Lookup, m&#233;thode
Récupère la valeur du type V associé à la clé spécifiée de type K.  
  
## Syntaxe  
  
```cpp  
V Lookup(  
   K key  
);  
```  
  
#### Paramètres  
 `key`  
 Clé utilisée pour rechercher un élément dans le UnorderedMapView. Le type de `key` est le nom de type *K*.  
  
## Valeur de retour  
 Valeur associée à `key`. Le type de la valeur de retour est le nom de type *V*.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::UnorderedMapView, classe](../cppcx/platform-collections-unorderedmapview-class.md)