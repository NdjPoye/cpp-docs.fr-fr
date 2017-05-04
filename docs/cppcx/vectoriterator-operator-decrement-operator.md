---
title: "VectorIterator::operator-- (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator--"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator-- (opérateur)"
ms.assetid: 650a3037-2984-4110-9d7c-cd3756e5f4b9
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator-- (op&#233;rateur)
Décrémente le VectorIterator actif.  
  
## Syntaxe  
  
```  
  
VectorIterator& operator--();  
VectorIterator operator--(  
   int  
);  
```  
  
## Valeur de retour  
 La première syntaxe décrémente le VectorIterator actif puis le retourne. La deuxième syntaxe retourne une copie du VectorIterator actif puis décrémente le VectorIterator actif.  
  
## Notes  
 La première syntaxe VectorIterator prédécrémente le VectorIterator actif.  
  
 La deuxième syntaxe post\-décrémente le VectorIterator actif. Le type `int` dans la deuxième syntaxe n’indique pas un opérande entier réel mais une post\-décrémentation.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorIterator, classe](../cppcx/platform-collections-vectoriterator-class.md)