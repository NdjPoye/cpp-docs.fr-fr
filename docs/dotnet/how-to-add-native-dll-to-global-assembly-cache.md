---
title: "Comment&#160;: ajouter une DLL native au Global Assembly Cache | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL (C++), natifs"
  - "Global Assembly Cache (GAC), charger des DLL natives"
  - "DLL natives (C++)"
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: ajouter une DLL native au Global Assembly Cache
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez placer une DLL native \(pas COM\) dans le Global Assembly Cache.  
  
## Exemple  
 **\/ASSEMBLYLINKRESOURCE** vous permet d'incorporer une DLL native dans un assembly.  
  
 Pour plus d'informations, consultez [\/ASSEMBLYLINKRESOURCE \(Lien vers une ressource du .NET Framework\)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md).  
  
```  
/ASSEMBLYLINKRESOURCE:MyComponent.dll  
```  
  
## Voir aussi  
 [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)