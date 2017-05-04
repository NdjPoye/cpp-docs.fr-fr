---
title: "Constructeurs de tableaux | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::Array::Array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Array::Array"
ms.assetid: befb8088-3915-4b5c-b7fd-90f79961412d
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Constructeurs de tableaux
Initialise un tableau unidimensionnel modifiable de types spécifiés par le paramètre de modèle de classe *T*.  
  
## Syntaxe  
  
```  
  
Array(unsigned int size);  
Array(T* data, unsigned int size);  
  
```  
  
#### Paramètres  
 `T`  
 Paramètre de modèle de classe.  
  
 `size`  
 Nombre d’éléments dans le tableau.  
  
 `data`  
 Pointeur vers un tableau de données de type `T` utilisé pour initialiser l'objet Array.  
  
## Notes  
 Pour plus d'informations sur la création d'instances de Platform::Array, consultez [Array et WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
## Configuration requise  
 **En\-tête :** vccorlib.h  
  
 **Espace de noms :** Platform  
  
## Voir aussi  
 [Platform::Array \(classe\)](../cppcx/platform-array-class.md)