---
title: "UnorderedMap::Insert, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::Insert"
ms.assetid: 89d55301-3cad-4877-825b-35096a1dd740
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::Insert, m&#233;thode
Ajoute une paire clé\-valeur spécifiée à l'objet UnorderedMap actif.  
  
## Syntaxe  
  
```cpp  
  
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
 `true` si la clé d'un élément existant dans les correspondances de l'objet Map actuel `key` et si la partie de la valeur de cet élément a la valeur `value`.`false` si aucun élément existant dans l'objet Map actif ne correspond à `key` et que les paramètres `key` et `value` sont transformés en paire clé\-valeur puis ajoutés à l'objet UnorderedMap actif.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections