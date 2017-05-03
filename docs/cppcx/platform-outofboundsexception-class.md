---
title: "Platform::OutOfBoundsException, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::OutOfBoundsException"
  - "Platform/Platform::OutOfBoundsException::OutOfBoundsException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::OutOfBoundsException"
ms.assetid: 96f8bf75-1207-4049-964b-7771822cadf3
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Platform::OutOfBoundsException, classe
Levée lorsqu'une opération tente d'accéder aux données en dehors de la plage valide.  
  
## Syntaxe  
  
```cpp  
public ref class OutOfBoundsException : COMException,    IException,    IPrintable,    IEquatable  
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