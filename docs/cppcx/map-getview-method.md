---
title: "Map::GetView (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::GetView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::GetView (méthode)"
ms.assetid: d432bb98-d354-4caa-8c2b-794406ac0b0b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::GetView (m&#233;thode)
Retourne une vue en lecture seule de l’objet Map actif. Autrement dit, une [classe Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md) qui implémente l’interface [Windows::Foundation::Collections::IMapView\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226037.aspx).  
  
## Syntaxe  
  
```  
  
Windows::Foundation::Collections::IMapView<K, V>^   
   GetView();  
```  
  
## Valeur de retour  
 Objet `MapView`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::Map, classe](../cppcx/platform-collections-map-class.md)   
 [Platform::Collections::UnorderedMapClass](../cppcx/platform-collections-unorderedmap-class.md)   
 [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)