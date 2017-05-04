---
title: "Platform::OutOfMemoryException, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::OutOfMemoryException"
  - "Platform/Platform::OutOfMemoryException::OutOfMemoryException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::OutOfMemoryException"
ms.assetid: 49c19f6b-f66c-4448-b861-91dcbf32de2c
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Platform::OutOfMemoryException, classe
Levée en cas de mémoire insuffisante pour terminer l'opération.  
  
## Syntaxe  
  
```cpp  
public ref class OutOfMemoryException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
## Notes  
 Pour plus d'informations, consultez la classe [COMException](../cppcx/platform-comexception-class.md).  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Platform::COMException \(classe\)](../cppcx/platform-comexception-class.md)