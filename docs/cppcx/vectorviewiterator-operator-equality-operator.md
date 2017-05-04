---
title: "VectorViewIterator::operator== (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator== (opérateur)"
ms.assetid: 89534116-5035-413b-89d3-073eedb88337
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator== (op&#233;rateur)
Indique si le VectorViewIterator actif est égal à un VectorViewIterator spécifié.  
  
## Syntaxe  
  
```  
bool operator==(  
   const VectorViewIterator& other  
) const;  
```  
  
#### Paramètres  
 `other`  
 Un autre VectorViewIterator.  
  
## Valeur de retour  
 `true` si l’objet VectorViewIterator actif est égal à `other` ; sinon, `false`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorViewIterator, classe](../cppcx/platform-collections-vectorviewiterator-class.md)