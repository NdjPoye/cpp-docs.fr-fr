---
title: "UnorderedMap::HasKey, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::HasKey"
ms.assetid: 7c397cdc-82f6-470a-8a3c-f5ba2cc58ed6
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::HasKey, m&#233;thode
Détermine si le UnorderedMap actif contient la clé spécifiée.  
  
## Syntaxe  
  
```scr  
  
bool HasKey(  
   K key  
);  
```  
  
#### Paramètres  
 `key`  
 Clé utilisée pour rechercher l'élément UnorderedMap. Le type de `key` est le nom de type *K*.  
  
## Valeur de retour  
 `true` si la clé est trouvée ; sinon, `false`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::UnorderedMap, classe](../cppcx/platform-collections-unorderedmap-class.md)   
 [Collections](../cppcx/collections-c-cx.md)   
 [Windows::Foundation::Collections::IKeyValuePair\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226031.aspx)