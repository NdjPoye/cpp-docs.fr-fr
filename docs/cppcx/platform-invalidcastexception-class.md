---
title: "Platform::InvalidCastException, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::InvalidCastException::InvalidCastException"
  - "Platform/Platform::InvalidCastException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::InvalidCastException"
ms.assetid: 0215131d-1251-4913-9561-824410e045b6
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Platform::InvalidCastException, classe
Levée lorsqu'un cast ou une conversion explicite n'est pas valide.  
  
## Syntaxe  
  
```cpp  
public ref class InvalidCastException : COMException,    IException,    IPrintable,    IEquatable  
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