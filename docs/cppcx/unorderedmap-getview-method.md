---
title: "UnorderedMap::GetView, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::GetView"
ms.assetid: 41a12802-3f42-461c-a6fc-a35fc34517f2
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::GetView, m&#233;thode
Retourne une vue en lecture seule de l’objet UnorderedMap actif, c’est\-à\-dire un [Platform::Collections::UnorderedMapView, classe](../cppcx/platform-collections-unorderedmapview-class.md) qui implémente l’interface [Windows::Foundation::Collections::IMapView::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx).  
  
## Syntaxe  
  
```scr  
  
Windows::Foundation::Collections::IMapView<K, V>^   
   GetView();  
```  
  
## Valeur de retour  
 Objet `UnorderedMapView`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Collections](../cppcx/collections-c-cx.md)   
 [Platform::Collections::UnorderedMap, classe](../cppcx/platform-collections-unorderedmap-class.md)   
 [Platform::Collections::UnorderedMapView, classe](../cppcx/platform-collections-unorderedmapview-class.md)