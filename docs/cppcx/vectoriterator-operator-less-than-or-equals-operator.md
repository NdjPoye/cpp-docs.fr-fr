---
title: "VectorIterator::operator&lt;= (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator<="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator<= (opérateur)"
ms.assetid: 57d3c269-77a5-4731-a3b4-dcda2758da19
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator&lt;= (op&#233;rateur)
Indique si l'objet VectorIterator actuel est inférieur ou égal à un objet VectorIterator spécifié.  
  
## Syntaxe  
  
```cpp  
  
bool operator<=(  
   const VectorIterator& other  
) const   
```  
  
#### Paramètres  
 `other`  
 Autre objet VectorIterator.  
  
## Valeur de retour  
 `true` si le VectorIterator actif est supérieur ou égal à `other` ; sinon, `false`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorIterator, classe](../cppcx/platform-collections-vectoriterator-class.md)