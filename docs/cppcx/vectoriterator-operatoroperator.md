---
title: "VectorIterator::operatorOperator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator[] (opérateur)"
ms.assetid: e1ba8101-8c16-4be1-b31b-91099d6e81f3
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operatorOperator
Récupère une référence à l'élément qui est un décalage spécifié à partir de l'objet VectorIterator actuel.  
  
## Syntaxe  
  
```  
  
reference operator[](difference_type n) const;  
```  
  
#### Paramètres  
 `n`  
 Déplacement d'un entier.  
  
## Valeur de retour  
 Élément qui est décalé par les éléments `n` à partir du VectorIterator actif.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorIterator, classe](../cppcx/platform-collections-vectoriterator-class.md)