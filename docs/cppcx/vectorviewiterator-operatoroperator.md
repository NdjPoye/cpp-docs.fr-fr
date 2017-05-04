---
title: "VectorViewIterator::operator, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator[] (opérateur)"
ms.assetid: 41bf327d-2037-457c-83df-6338fc1abbc2
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator, op&#233;rateur
Extrait une référence à l'élément qui est un offset spécifié de l'objet VectorViewIterator actuel.  
  
## Syntaxe  
  
```  
reference operator[](difference_type n) const;  
```  
  
#### Paramètres  
 `n`  
 Déplacement d'un entier.  
  
## Valeur de retour  
 Élément qui est déplacé par les éléments `n` de l'objet VectorViewIterator actuel.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorViewIterator, classe](../cppcx/platform-collections-vectorviewiterator-class.md)