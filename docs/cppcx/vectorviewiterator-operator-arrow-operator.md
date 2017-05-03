---
title: "VectorViewIterator::operator-&gt; (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator-> (opérateur)"
ms.assetid: cc02cfa2-dfcb-4fb7-b4a0-c290f91aa4a6
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator-&gt; (op&#233;rateur)
Récupère l'adresse de l'élément référencé par le VectorViewIterator actif.  
  
## Syntaxe  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
## Valeur de retour  
 Valeur de l’élément référencé par le VectorViewIterator actif.  
  
 Le type de la valeur de retour est un type interne non spécifié nécessaire pour l’implémentation de cet opérateur.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorViewIterator, classe](../cppcx/platform-collections-vectorviewiterator-class.md)