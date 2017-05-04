---
title: "UnorderedMap::Lookup, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::Lookup"
ms.assetid: 6f9bb393-3791-423d-bfee-925e0531e1a5
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::Lookup, m&#233;thode
Récupère la valeur du type V associé à la clé spécifiée de type K.  
  
## Syntaxe  
  
```scr  
V Lookup(  
   K key  
);  
```  
  
#### Paramètres  
 `key`  
 Clé utilisée pour rechercher un élément dans l'objet UnorderedMap. Le type de `key` est le nom de type *K*.  
  
## Valeur de retour  
 Valeur associée à `key`. Le type de la valeur de retour est le nom de type *V*.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Collections](../cppcx/collections-c-cx.md)   
 [Platform::Collections::UnorderedMap, classe](../cppcx/platform-collections-unorderedmap-class.md)