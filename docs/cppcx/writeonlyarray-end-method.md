---
title: "WriteOnlyArray::end (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WriteOnlyArray::end (méthode)"
ms.assetid: 045045fe-f210-400b-b688-7abb95fc702a
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WriteOnlyArray::end (m&#233;thode)
Retourne un pointeur sur un point suivant au\-delà du dernier élément du tableau.  
  
## Syntaxe  
  
```cpp  
T* end() const;  
```  
  
## Valeur de retour  
 Itérateur de pointeur sur un point suivant au\-delà du dernier élément du tableau.  
  
## Notes  
 Cet itérateur peut être utilisé avec les algorithmes STL pour exécuter des opérations telles que `std::sort` sur les éléments de tableau.  
  
## Configuration requise  
 **En\-tête** : vccorlib.h  
  
 **Espace de noms :** Platform  
  
## Voir aussi  
 [Platform::WriteOnlyArray \(classe\)](../cppcx/platform-writeonlyarray-class.md)   
 [Array et WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)