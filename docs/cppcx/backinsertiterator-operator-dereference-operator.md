---
title: "BackInsertIterator::operator* (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator::operator*"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator::operator* (opérateur)"
ms.assetid: 68d70bc8-da84-49c6-ba35-4ac5aa6dad16
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# BackInsertIterator::operator* (op&#233;rateur)
Extrait une référence au BackInsertIterator actif.  
  
## Syntaxe  
  
```  
BackInsertIterator& operator*();  
```  
  
## Valeur de retour  
 Référence au BackInsertIterator actif.  
  
## Notes  
 Cet opérateur retourne une référence au BackInsertIterator actif, et non à un élément dans la collection actuelle.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::BackInsertIterator, classe](../cppcx/platform-collections-backinsertiterator-class.md)