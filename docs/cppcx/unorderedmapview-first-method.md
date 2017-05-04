---
title: "UnorderedMapView::First, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::First"
ms.assetid: 385f2a46-90ee-412b-817b-b5a0f2f57022
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::First, m&#233;thode
Retourne un itérateur qui spécifie le premier élément [Windows::Foundation::Collections::IKeyValuePair\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) de l’objet UnorderedMap.  
  
## Syntaxe  
  
```cpp  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^   
First();  
```  
  
## Valeur de retour  
 Itérateur qui spécifie le premier élément de la vue cartographique.  
  
## Notes  
 Un moyen pratique de contenir l'itérateur retourné par First\(\) est d'assigner la valeur de retour à une variable déclarée avec le mot clé de déduction de type [auto](~/cpp/auto-cpp.md). Par exemple, `auto x = myMapView->First();`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::UnorderedMapView, classe](../cppcx/platform-collections-unorderedmapview-class.md)