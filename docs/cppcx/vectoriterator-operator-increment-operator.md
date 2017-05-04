---
title: "VectorIterator::operator++ (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator++ (opérateur)"
ms.assetid: c46b18ff-45be-436a-8f31-b3a5ecc19b77
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator++ (op&#233;rateur)
Incrémente le VectorIterator actif.  
  
## Syntaxe  
  
```  
  
VectorIterator& operator++();  
VectorIterator operator++(  
   int  
);  
```  
  
## Valeur de retour  
 La première syntaxe incrémente le VectorIterator actif puis le retourne. La deuxième syntaxe retourne une copie du VectorIterator actif puis incrémente le VectorIterator actif.  
  
## Notes  
 La première syntaxe VectorIterator préincrémente le VectorIterator actif.  
  
 La deuxième syntaxe postincrémente le VectorIterator actif. Le type `int` dans la deuxième syntaxe n'indique pas un opérande entier réel mais une post\-incrémentation.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorIterator, classe](../cppcx/platform-collections-vectoriterator-class.md)