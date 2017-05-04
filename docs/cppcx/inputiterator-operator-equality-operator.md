---
title: "InputIterator::operator== (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InputIterator::operator== (opérateur)"
ms.assetid: 84f1b69a-77b9-467c-ad1a-2fe8a7c3009e
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# InputIterator::operator== (op&#233;rateur)
Indique si l'InputIterator actif est égal à un InputIterator spécifié.  
  
## Syntaxe  
  
```  
bool operator==(  
   const InputIterator& other  
) const;  
```  
  
#### Paramètres  
 `other`  
 Autre InputIterator.  
  
## Valeur de retour  
 `true` si l'InputIterator actif est égal à `other` ; sinon, `false`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::InputIterator, classe](../cppcx/platform-collections-inputiterator-class.md)