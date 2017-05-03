---
title: "Box::Box, constructeur | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::Box"
dev_langs: 
  - "C++"
ms.assetid: 3c4777f0-801c-4b24-9426-6d658dfaecf8
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::Box, constructeur
Crée un `Box` qui peut encapsuler une valeur du type spécifié.  
  
## Syntaxe  
  
```cpp  
Box(T valueArg);  
```  
  
#### Paramètres  
 `valueArg`  
 Type de la valeur boxed, par exemple `int`, `bool`, `float64`, `DateTime`.  
  
## Configuration requise  
 **En\-tête :** vccorlib.h  
  
 **Espace de noms :** Platform  
  
## Voir aussi  
 [Platform::Box, classe](../cppcx/platform-box-class.md)   
 [Boxing](../cppcx/boxing-c-cx.md)