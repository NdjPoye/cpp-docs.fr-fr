---
title: "Map::Insert, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::Insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::Insert"
ms.assetid: 3acb2221-c12f-407a-a570-2e52df3569f6
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::Insert, m&#233;thode
Ajoute une paire clé\-valeur spécifiée à l'objet Map actuel.  
  
## Syntaxe  
  
```  
  
virtual bool Insert(  
   K key,   
   V value  
);  
```  
  
#### Paramètres  
 `key`  
 Partie de clé de la paire clé\-valeur. Le type de `key` est le nom de type *K*.  
  
 `value`  
 Partie de valeur de la paire clé\-valeur. Le type de `value` est le nom de type *V*.  
  
## Valeur de retour  
 `true` si la clé d'un élément existant dans les correspondances de l'objet Map actuel `key` et si la partie de la valeur de cet élément a la valeur `value`.`false` si aucun élément existant dans les correspondances de l'objet Map actuel `key` et si les paramètres `key` et `value` sont transformés en paire clé\-valeur puis ajoutés à l'objet Map actuel.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::Map, classe](../cppcx/platform-collections-map-class.md)