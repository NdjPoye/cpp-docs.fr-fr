---
title: "UnorderedMapView::HasKey, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::HasKey"
ms.assetid: 4704da18-8606-4df7-be51-d125b2e4aee0
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::HasKey, m&#233;thode
Détermine si le UnorderedMap actif contient la clé spécifiée.  
  
## Syntaxe  
  
```cpp  
  
bool HasKey(  
   K key  
);  
```  
  
#### Paramètres  
 `key`  
 Clé utilisée pour rechercher l'élément. Le type de `key` est le nom de type *K*.  
  
## Valeur de retour  
 `true` si la clé est trouvée ; sinon, `false`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::UnorderedMap, classe](../cppcx/platform-collections-unorderedmap-class.md)   
 [Collections](../cppcx/collections-c-cx.md)   
 [Windows::Foundation::Collections::IKeyValuePair\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226031.aspx)