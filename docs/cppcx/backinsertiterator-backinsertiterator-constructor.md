---
title: "BackInsertIterator::BackInsertIterator (constructeur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator::BackInsertIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator::BackInsertIterator (constructeur)"
ms.assetid: ae6f0213-a7bb-43b8-9a5e-7a8dad7c76f8
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# BackInsertIterator::BackInsertIterator (constructeur)
Initialise une nouvelle instance de la classe `BackInsertIterator`.  
  
## Syntaxe  
  
```  
  
explicit BackInsertIterator(  
   Windows::Foundation::Collections::IVector<T>^ v  
);  
```  
  
#### Paramètres  
 `v`  
 Objet IVector\<T\>.  
  
## Notes  
 Un `BackInsertIterator` insère des éléments après le dernier élément de l'objet spécifié par le paramètre `v`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::BackInsertIterator, classe](../cppcx/platform-collections-backinsertiterator-class.md)