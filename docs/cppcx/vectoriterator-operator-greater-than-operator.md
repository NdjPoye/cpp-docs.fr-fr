---
title: "VectorIterator::operator&gt; (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator> (opérateur)"
ms.assetid: a9a323a4-d28a-4080-a48c-ed4c8ef2eafb
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator&gt; (op&#233;rateur)
Indique si le VectorIterator actif est supérieur au VectorIterator spécifié.  
  
## Syntaxe  
  
```cpp  
  
bool operator>(  
   const VectorIterator& other  
) const   
```  
  
#### Paramètres  
 `other`  
 Autre objet VectorIterator.  
  
## Valeur de retour  
 `true` si le VectorIterator actif est supérieur à `other`, sinon, `false`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorIterator, classe](../cppcx/platform-collections-vectoriterator-class.md)