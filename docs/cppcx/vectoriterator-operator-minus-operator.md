---
title: "VectorIterator::operator- (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator- (opérateur)"
ms.assetid: 5714c132-e973-47fd-901b-ba13da7b9372
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator- (op&#233;rateur)
Soustrait un nombre spécifié d'éléments de l'itérateur actuel en cédant un nouvel itérateur, ou un itérateur spécifié de l'itérateur actuel en cédant le nombre d'éléments entre les itérateurs.  
  
## Syntaxe  
  
```  
  
VectorIterator operator-(  
   difference_type n  
) const;  
  
difference_type operator-(  
   const VectorIterator& other  
) const;  
```  
  
#### Paramètres  
 `n`  
 Nombre d'éléments.  
  
 `other`  
 Autre objet VectorIterator.  
  
## Valeur de retour  
 La première syntaxe d’opérateur retourne un objet VectorIterator qui a `n` éléments en moins que l’objet VectorIterator actif. La deuxième syntaxe d’opérateur retourne le nombre d’éléments entre l’objet actif et l’objet VectorIterator `other`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorIterator, classe](../cppcx/platform-collections-vectoriterator-class.md)