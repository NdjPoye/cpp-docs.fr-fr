---
title: "UnorderedMapView::Split, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::Split"
ms.assetid: b759d254-40c9-40f1-9838-106ffb2c5626
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::Split, m&#233;thode
Divise l'objet UnorderedMapView actif en deux objets UnorderedMapView. Cette méthode n'est pas opérationnelle.  
  
## Syntaxe  
  
```cpp  
void Split(  
   Windows::Foundation::Collections::IMapView<  
                         K,  
                         V>^ * firstPartition,  
   Windows::Foundation::Collections::IMapView<  
                         K,  
                         V>^ * secondPartition  
);  
```  
  
#### Paramètres  
 `firstPartition`  
 Première partie de l'objet UnorderedMapView d'origine.  
  
 `secondPartition`  
 Deuxième partie de l'objet UnorderedMapView d'origine.  
  
## Notes  
 Cette méthode n'est pas opérationnelle. Elle ne fait rien.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::UnorderedMapView, classe](../cppcx/platform-collections-unorderedmapview-class.md)