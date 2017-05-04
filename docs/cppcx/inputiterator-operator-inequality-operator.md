---
title: "InputIterator::operator!= (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator::operator!="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InputIterator::operator!= (opérateur)"
ms.assetid: 68a33a74-4bf9-4c91-858e-9c621861b81e
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# InputIterator::operator!= (op&#233;rateur)
Indique si l'InputIterator actif n'est pas égal à un InputIterator spécifié.  
  
## Syntaxe  
  
```  
bool operator!=(  
   const InputIterator& other  
) const;  
```  
  
#### Paramètres  
 `other`  
 Autre InputIterator.  
  
## Valeur de retour  
 `true` si l'InputIterator actif n'est pas égal à `other` ; sinon, `false`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::InputIterator, classe](../cppcx/platform-collections-inputiterator-class.md)