---
title: "Box::operator Box&lt;T&gt;^, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator Box<T>^"
dev_langs: 
  - "C++"
ms.assetid: c2c89385-c334-4b09-8f87-d46ea4809232
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::operator Box&lt;T&gt;^, op&#233;rateur
Permet les conversions par boxing d'une classe value `T` en `Box<T>`.  
  
## Syntaxe  
  
```cpp  
operator Box<const T>^(const T valueType);  
```  
  
#### Paramètres  
 `T`  
 Tout type enum, de classe value ou de struct value. Inclut les types intégrés dans [espace de noms par défaut](../cppcx/default-namespace.md).  
  
## Valeur de retour  
 Instance `Platform::Box<T>``^` qui représente la valeur d'origine convertie par boxing en une classe ref.  
  
## Configuration requise  
 **En\-tête :** vccorlib.h  
  
 **Espace de noms :** Platform  
  
## Voir aussi  
 [Platform::Box, classe](../cppcx/platform-box-class.md)   
 [Platform::IBox, interface](../cppcx/platform-ibox-interface.md)   
 [Boxing](../cppcx/boxing-c-cx.md)