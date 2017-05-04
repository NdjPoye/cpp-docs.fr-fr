---
title: "MapView::Lookup (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::Lookup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::Lookup (méthode)"
ms.assetid: 93090ac3-3f1d-4b7e-b80e-164b8c65cd29
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::Lookup (m&#233;thode)
Récupère la valeur du type V associé à la clé spécifiée de type K.  
  
## Syntaxe  
  
```  
V Lookup(  
   K key  
);  
```  
  
#### Paramètres  
 `key`  
 Clé utilisée pour trouver un élément dans le MapView. Le type de `key` est le nom de type *K*.  
  
## Valeur de retour  
 Valeur associée à `key`. Le type de la valeur de retour est le nom de type *V*.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::MapView, classe](../cppcx/platform-collections-mapview-class.md)