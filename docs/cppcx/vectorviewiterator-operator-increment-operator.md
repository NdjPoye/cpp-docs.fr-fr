---
title: "VectorViewIterator::operator++ (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator++ (opérateur)"
ms.assetid: 5391e6e2-a7ee-4dab-8cee-b2237894246f
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator++ (op&#233;rateur)
Incrémente l'objet VectorViewIterator actuel.  
  
## Syntaxe  
  
```  
  
VectorViewIterator& operator++();  
VectorViewIterator operator++(  
   int  
);  
```  
  
## Valeur de retour  
 La première syntaxe incrémente l'objet VectorViewIterator actuel, puis le retourne. La deuxième syntaxe retourne une copie de l'objet VectorViewIterator actuel, puis l'incrémente.  
  
## Notes  
 La première syntaxe VectorViewIterator préincrémente l'objet VectorViewIterator actuel.  
  
 La deuxième syntaxe postincrémente l'objet VectorViewIterator actuel. Le type `int` dans la deuxième syntaxe n'indique pas un opérande entier réel mais une post\-incrémentation.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorViewIterator, classe](../cppcx/platform-collections-vectorviewiterator-class.md)