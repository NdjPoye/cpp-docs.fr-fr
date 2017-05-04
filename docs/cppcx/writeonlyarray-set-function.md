---
title: "WriteOnlyArray::set (fonction) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WriteOnlyArray::set (fonction)"
ms.assetid: 0359f922-f25e-47d1-b7df-87e7fd0f76e5
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WriteOnlyArray::set (fonction)
Définit la valeur spécifiée à l'index spécifié dans le tableau.  
  
## Syntaxe  
  
```cpp  
T& set(  
   unsigned int indexArg,  
   T valueArg);  
```  
  
#### Paramètres  
 `indexArg`  
 Index de l'élément à définir.  
  
 `valueArg`  
 Valeur à définir à `indexArg`.  
  
## Valeur de retour  
 Référence à l'élément qui vient d'être défini.  
  
## Configuration requise  
 **En\-tête** : vccorlib.h  
  
 **Espace de noms :** Platform  
  
## Voir aussi  
 [Platform::WriteOnlyArray \(classe\)](../cppcx/platform-writeonlyarray-class.md)   
 [Array et WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)