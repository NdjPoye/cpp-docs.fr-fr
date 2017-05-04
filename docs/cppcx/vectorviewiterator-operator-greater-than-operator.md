---
title: "VectorViewIterator::operator&gt; (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator> (opérateur)"
ms.assetid: c689b677-e3c6-4f6e-8e3a-54d5f2a6123d
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator&gt; (op&#233;rateur)
Indique si le VectorViewIterator actif est supérieur à un VectorViewIterator spécifié.  
  
## Syntaxe  
  
```  
  
bool operator>(  
   const VectorViewIterator& other  
) const;  
```  
  
#### Paramètres  
 `other`  
 Un autre VectorViewIterator.  
  
## Valeur de retour  
 `true` si le VectorViewIterator actif est supérieur à `other` ; sinon, `false`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorViewIterator, classe](../cppcx/platform-collections-vectorviewiterator-class.md)