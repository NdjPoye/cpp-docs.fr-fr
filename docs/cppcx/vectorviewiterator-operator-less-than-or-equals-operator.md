---
title: "VectorViewIterator::operator&lt;= (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator<="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator<= (opérateur)"
ms.assetid: 523bf6ca-fb45-498b-8e94-fa8a093dd4ad
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator&lt;= (op&#233;rateur)
Indique si l'objet VectorIterator actuel est inférieur ou égal à un objet VectorIterator spécifié.  
  
## Syntaxe  
  
```  
  
bool operator<=(  
   const VectorViewIterator& other  
) const;  
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
 [Platform::Collections::VectorViewIterator, classe](../cppcx/platform-collections-vectorviewiterator-class.md)