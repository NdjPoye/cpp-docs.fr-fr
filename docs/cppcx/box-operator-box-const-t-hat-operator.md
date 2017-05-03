---
title: "Box::operator Box&lt;const T&gt;^, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator Box<const T>^"
dev_langs: 
  - "C++"
ms.assetid: c43a2e8f-7e9d-4587-960f-1bab48923f82
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::operator Box&lt;const T&gt;^, op&#233;rateur
Permet les conversions par boxing d'une classe value `const``T` ou d'une classe `enum``T` en `Box<T>`.  
  
## Syntaxe  
  
```cpp  
operator Box<const T>^(const T valueType);  
```  
  
#### Paramètres  
 `T`  
 Toute classe value, tout struct value ou tout type enum. Inclut les types intégrés dans [espace de noms par défaut](../cppcx/default-namespace.md).  
  
## Valeur de retour  
 Instance `Platform::Box<T>``^` qui représente la valeur d'origine convertie par boxing en une classe ref.  
  
## Configuration requise  
 **En\-tête :** vccorlib.h  
  
 **Espace de noms :** Platform  
  
## Voir aussi  
 [Platform::Box, classe](../cppcx/platform-box-class.md)   
 [Platform::IBox, interface](../cppcx/platform-ibox-interface.md)