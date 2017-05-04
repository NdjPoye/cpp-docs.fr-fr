---
title: "BackInsertIterator::operator++ (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator::operator++ (opérateur)"
ms.assetid: 08324574-db2b-4d95-825e-a93a56f327da
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# BackInsertIterator::operator++ (op&#233;rateur)
Retourne une référence au BackInsertIterator actif. L'itérateur est pas modifié.  
  
## Syntaxe  
  
```  
  
BackInsertIterator& operator++();  
  
BackInsertIterator operator++(  
   int  
);  
```  
  
## Valeur de retour  
 Référence au BackInsertIterator actif.  
  
## Notes  
 Par conception, le premier exemple de syntaxe préincrémente le BackInsertIterator actuel et la deuxième syntaxe postincrémente le BackInsertIterator actuel. Le type `int` dans la deuxième syntaxe n'indique pas un opérande entier réel mais une post\-incrémentation.  
  
 Toutefois, cet opérateur ne modifie pas réellement le BackInsertIterator. Au lieu de cela, l'opérateur retourne une référence à l'itérateur actuel non modifié. Ce comportement est le même que pour [operator\*](../cppcx/backinsertiterator-operator-dereference-operator.md).  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::BackInsertIterator, classe](../cppcx/platform-collections-backinsertiterator-class.md)