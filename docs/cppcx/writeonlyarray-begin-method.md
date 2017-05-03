---
title: "WriteOnlyArray::begin (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WriteOnlyArray::begin (méthode)"
ms.assetid: 25025fa0-8f55-4abf-93ad-71db45ddfae3
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WriteOnlyArray::begin (m&#233;thode)
Retourne un pointeur désignant le premier élément du tableau.  
  
## Syntaxe  
  
```cpp  
T* begin() const;  
```  
  
## Valeur de retour  
 Pointeur désignant le premier élément du tableau.  
  
## Notes  
 Cet itérateur peut être utilisé avec les algorithmes STL tels que `std::sort` pour exécuter des opérations sur les élément du tableau.  
  
## Configuration requise  
 **En\-tête** : vccorlib.h  
  
 **Espace de noms :** Platform  
  
## Voir aussi  
 [Platform::WriteOnlyArray \(classe\)](../cppcx/platform-writeonlyarray-class.md)   
 [Array et WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)