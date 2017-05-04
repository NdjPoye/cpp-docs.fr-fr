---
title: "VectorViewIterator::operator&lt; (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator< (opérateur)"
ms.assetid: 411c9af9-78b1-4b1b-839b-3bec76020184
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator&lt; (op&#233;rateur)
Indique si le VectorIterator actuel est inférieur au VectorIterator spécifié.  
  
## Syntaxe  
  
```  
bool operator<(  
   const VectorViewIterator& other  
) const;  
```  
  
#### Paramètres  
 `other`  
 Autre objet VectorIterator.  
  
## Valeur de retour  
 `true` si le VectorIterator actuel est inférieur à `other` ; sinon, `false`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorViewIterator, classe](../cppcx/platform-collections-vectorviewiterator-class.md)