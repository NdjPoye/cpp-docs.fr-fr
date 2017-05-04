---
title: "Box::Value, propri&#233;t&#233; | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::Value"
dev_langs: 
  - "C++"
ms.assetid: f456b105-6c14-4737-8c27-ad47d1eabd32
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::Value, propri&#233;t&#233;
Retourne la valeur qui est encapsulée dans l'objet `Box`.  
  
## Syntaxe  
  
```cpp  
virtual property T Value{  
   T get();  
}  
```  
  
## Valeur de retour  
 Retourne la valeur boxed avec le même type que celui avant la conversion par boxing.  
  
## Configuration requise  
 **En\-tête :** vccorlib.h  
  
 **Espace de noms :** Platform  
  
## Voir aussi  
 [Platform::Box, classe](../cppcx/platform-box-class.md)   
 [Boxing](../cppcx/boxing-c-cx.md)