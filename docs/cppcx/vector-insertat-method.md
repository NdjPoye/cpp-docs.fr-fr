---
title: "Vector::InsertAt, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::InsertAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::InsertAt"
ms.assetid: 05b2ca08-234e-4fc0-acfd-cafa148d1577
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::InsertAt, m&#233;thode
Insère l'élément spécifié dans le vecteur actuel après l'identification de l'élément par l'index spécifié.  
  
## Syntaxe  
  
```  
  
virtual void InsertAt(  
   unsigned int index,   
   T item)  
```  
  
#### Paramètres  
 `index`  
 Entier non signé de base zéro qui spécifie un élément particulier dans l'objet Vector.  
  
 `item`  
 Élément à insérer dans l'objet Vector après l'élément spécifié par `index`. Le type de `item` est défini par le nom de type *T*.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::Vector, classe](../cppcx/platform-collections-vector-class.md)