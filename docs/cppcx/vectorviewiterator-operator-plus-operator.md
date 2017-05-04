---
title: "VectorViewIterator::operator+ (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator+"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator+ (opérateur)"
ms.assetid: 8206de2f-61b3-49cd-9715-d57695d880b3
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator+ (op&#233;rateur)
Retourne un VectorIterator qui référence l'élément au décalage spécifié à partir du VectorViewIterator spécifié.  
  
## Syntaxe  
  
```  
  
VectorViewIterator operator+(  
   difference_type n  
) const;  
  
template <  
   typename T  
>   
inline VectorViewIterator<T> operator+  
   (ptrdiff_t n,   
   const VectorViewIterator<T>& i  
);  
  
```  
  
#### Paramètres  
 `T`  
 Dans la deuxième syntaxe, typename du VectorViewIterator.  
  
 `n`  
 Déplacement d'un entier.  
  
 `i`  
 Dans la deuxième syntaxe, un VectorViewIterator.  
  
## Valeur de retour  
 Dans la première syntaxe, VectorViewIterator qui fait référence à l’élément spécifié au décalage spécifié par rapport au VectorViewIterator actuel.  
  
 Dans la deuxième syntaxe, VectorViewIterator qui fait référence à l’élément au décalage spécifié par rapport au début du paramètre `i`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorViewIterator, classe](../cppcx/platform-collections-vectorviewiterator-class.md)