---
title: "MapView::HasKey (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::HasKey"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::HasKey (méthode)"
ms.assetid: c1a24f63-e6fd-4cfd-90ce-b89352b98324
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::HasKey (m&#233;thode)
Détermine si le MapView actif contient la clé spécifiée.  
  
## Syntaxe  
  
```  
  
bool HasKey(  
   K key  
);  
```  
  
#### Paramètres  
 `key`  
 Clé utilisée pour rechercher l’élément MapView. Le type de `key` est le nom de type *K*.  
  
## Valeur de retour  
 `true` si la clé est trouvée ; sinon, `false`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::MapView, classe](../cppcx/platform-collections-mapview-class.md)