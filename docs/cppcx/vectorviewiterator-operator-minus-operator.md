---
title: "VectorViewIterator::operator- (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator- (opérateur)"
ms.assetid: 03935872-8acc-4919-ae14-f375ca738aac
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator- (op&#233;rateur)
Soustrait un nombre spécifié d'éléments de l'itérateur actuel en cédant un nouvel itérateur, ou un itérateur spécifié de l'itérateur actuel en cédant le nombre d'éléments entre les itérateurs.  
  
## Syntaxe  
  
```  
  
VectorViewIterator operator-(  
   difference_type n  
) const;  
  
difference_type operator-(  
   const VectorViewIterator& other  
) const;  
```  
  
#### Paramètres  
 `n`  
 Nombre d'éléments.  
  
 `other`  
 Un autre VectorViewIterator.  
  
## Valeur de retour  
 La première syntaxe d'opérateur retourne un objet VectorViewIterator qui a un nombre inférieur d'éléments `n` par rapport à l'objet VectorViewIterator actuel. La deuxième syntaxe d'opérateur retourne le nombre d'éléments entre l'objet actuel et l'objet VectorViewIterator `other`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorViewIterator, classe](../cppcx/platform-collections-vectorviewiterator-class.md)