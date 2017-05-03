---
title: "MapView::Split (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::Split"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::Split (méthode)"
ms.assetid: b863e223-2282-4d1a-b995-77a690120542
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::Split (m&#233;thode)
Divise l'objet MapView actif en deux objets MapView. Cette méthode n'est pas opérationnelle.  
  
## Syntaxe  
  
```  
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
 Première partie de l'objet MapView d'origine.  
  
 `secondPartition`  
 Deuxième partie de l'objet MapView d'origine.  
  
## Notes  
 Cette méthode n'est pas opérationnelle. Elle ne fait rien.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::MapView, classe](../cppcx/platform-collections-mapview-class.md)