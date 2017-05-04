---
title: "to_vector (fonction) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::to_vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "to_vector (fonction)"
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# to_vector (fonction)
Retourne un `std::vector` dont la valeur est la même que la collection sous\-jacente du paramètre IVector ou IVectorView spécifié.  
  
## Syntaxe  
  
```  
template <  
   typename T  
>  
inline ::std::vector<T> to_vector(  
   IVector<T>^ v  
);  
template <  
   typename T  
>  
inline ::std::vector<T> to_vector(  
   IVectorView<T>^ v  
);  
```  
  
#### Paramètres  
 `T`  
 Paramètre de type de modèle.  
  
 `v`  
 Interface IVector ou IVectorView qui permet d'accéder à un objet Vector ou VectorView sous\-jacent.  
  
## Valeur de retour  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Windows::Foundation::Collections  
  
## Voir aussi  
 [Windows::Foundation::Collections, espace de noms](../cppcx/windows-foundation-collections-namespace-c-cx.md)