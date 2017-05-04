---
title: "Map::Lookup (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::Lookup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::Lookup (méthode)"
ms.assetid: c56773ae-2df0-4d21-a6ab-9603529547b0
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::Lookup (m&#233;thode)
Récupère la valeur de type V associée à la clé spécifiée de type K si la clé existe.  
  
## Syntaxe  
  
```  
V Lookup(  
   K key  
);  
```  
  
#### Paramètres  
 `key`  
 Clé utilisée pour trouver un élément dans le Map. Le type de `key` est le nom de type *K*.  
  
## Valeur de retour  
 Valeur associée à `key`. Le type de la valeur de retour est le nom de type *V*.  
  
## Notes  
 Si la clé n'existe pas, l'exception [Platform::OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md) est levée.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::Map, classe](../cppcx/platform-collections-map-class.md)   
 [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)