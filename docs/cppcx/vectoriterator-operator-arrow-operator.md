---
title: "VectorIterator::operator-&gt; (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator-> (opérateur)"
ms.assetid: d6caed5c-4899-45f8-95a2-687eafeeb8e1
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator-&gt; (op&#233;rateur)
Récupère l'adresse de l'élément référencé par le VectorIterator actif.  
  
## Syntaxe  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
## Valeur de retour  
 Valeur de l’élément référencé par le VectorIterator actif.  
  
 Le type de la valeur de retour est un type interne non spécifié nécessaire pour l’implémentation de cet opérateur.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorIterator, classe](../cppcx/platform-collections-vectoriterator-class.md)