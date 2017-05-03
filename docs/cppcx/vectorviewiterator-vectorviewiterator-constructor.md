---
title: "VectorViewIterator::VectorViewIterator (constructeur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::VectorViewIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::VectorViewIterator (constructeur)"
ms.assetid: 30bf643a-4100-4547-b34c-ce16c89f78ed
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::VectorViewIterator (constructeur)
Initialise une nouvelle instance de la classe VectorViewIterator.  
  
## Syntaxe  
  
```  
  
VectorViewIterator();  
  
explicit VectorViewIterator(  
   Windows::Foundation::Collections::IVectorView<T>^ v  
);  
```  
  
#### Paramètres  
 `v`  
 Objet IVectorView\<T\>.  
  
## Notes  
 Le premier exemple de syntaxe est le constructeur par défaut. Le deuxième exemple de syntaxe est un constructeur explicite qui est utilisé pour construire un VectorViewIterator à partir d'un objet IVectorView\<T\>.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::VectorViewIterator, classe](../cppcx/platform-collections-vectorviewiterator-class.md)