---
title: "VectorIterator::operator== (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator== (opérateur)"
ms.assetid: 1152153c-a564-40bb-8924-a3c6a0ea3752
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator== (op&#233;rateur)
Indique si l'objet VectorIterator actuel est égal à un objet VectorIterator spécifié.  
  
## Syntaxe  
  
```  
bool operator==(  
   const VectorIterator& other  
) const;  
```  
  
#### Paramètres  
 `other`  
 Autre objet VectorIterator.  
  
## Valeur de retour  
 `true` si l'objet VectorIterator actuel est égal à `other` ; sinon, `false`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorIterator, classe](../cppcx/platform-collections-vectoriterator-class.md)