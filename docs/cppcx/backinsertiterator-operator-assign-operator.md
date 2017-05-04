---
title: "BackInsertIterator::operator= (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator::operator= (opérateur)"
ms.assetid: 509c9b4c-14fb-4318-bf65-b8926cc72f4f
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# BackInsertIterator::operator= (op&#233;rateur)
Ajoute l'objet spécifié à la fin de la collection séquentielle en cours.  
  
## Syntaxe  
  
```  
  
BackInsertIterator& operator=(  
   const T& t  
);  
```  
  
#### Paramètres  
 `t`  
 Objet à ajouter à la collection actuelle.  
  
## Valeur de retour  
 Référence au BackInsertIterator actif.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::BackInsertIterator, classe](../cppcx/platform-collections-backinsertiterator-class.md)