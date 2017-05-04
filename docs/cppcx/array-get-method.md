---
title: "Array::get (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::Array::get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Array::get (méthode)"
ms.assetid: 3bbcd829-35e7-4912-99ba-6ab9de407287
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Array::get (m&#233;thode)
Extrait une référence à l'élément de tableau à la position d'index spécifiée.  
  
## Syntaxe  
  
```  
  
T& get(  
unsigned int index  
)  const;  
```  
  
#### Paramètres  
 `index`  
 Index de base zéro qui identifie un élément du tableau. L'index minimale est 0 et l'index maximal est la valeur spécifiée par le paramètre `size` dans le [constructeur de tableau](../cppcx/array-constructors.md).  
  
## Valeur de retour  
 Élément de tableau spécifié par le paramètre `index`.  
  
## Configuration requise  
 **En\-tête :** vccorlib.h  
  
 **Espace de noms :** Platform  
  
## Voir aussi  
 [Platform::Array \(classe\)](../cppcx/platform-array-class.md)