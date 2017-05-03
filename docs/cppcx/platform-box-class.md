---
title: "Platform::Box, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box"
dev_langs: 
  - "C++"
ms.assetid: b3d7ea37-e98a-4fbc-80b0-ad35e50250c6
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::Box, classe
Permet à un type valeur comme `Windows::Foundation::DateTime` ou à un type scalaire comme `int` d’être stocké dans un type `Platform::Object`. Vous n’avez généralement pas besoin d’utiliser `Box` explicitement, car le boxing s’effectue implicitement lors de la conversion d’un type valeur en `Object^`.  
  
## Syntaxe  
  
```cpp  
ref class Box abstract;  
```  
  
## Notes  
  
## Configuration requise  
 **En\-tête :** vccorlib.h  
  
 **Espace de noms :** Platform  
  
## Voir aussi  
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)   
 [Boxing](../cppcx/boxing-c-cx.md)