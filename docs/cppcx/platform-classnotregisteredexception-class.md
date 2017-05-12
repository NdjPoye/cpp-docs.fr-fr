---
title: "Platform::ClassNotRegisteredException, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::ClassNotRegisteredException::ClassNotRegisteredException"
  - "Platform/Platform::ClassNotRegisteredException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::ClassNotRegisteredException"
ms.assetid: 8f8871d8-51b9-46e8-902e-ae023c9f1de9
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Platform::ClassNotRegisteredException, classe
Levée lorsqu'une classe COM n'a pas été inscrite.  
  
## Syntaxe  
  
```cpp  
public ref class ClassNotRegisteredException : COMException,    IException,    IPrintable,    IEquatable  
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