---
title: "Platform::NotImplementedException, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::NotImplementedException"
  - "Platform/Platform::NotImplementedException::NotImplementedException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::NotImplementedException"
ms.assetid: 6da26cc2-dde8-4aea-aa85-67aac55cf97b
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Platform::NotImplementedException, classe
Levée lorsqu'un membre d'interface n'est pas implémenté dans un type dérivé.  
  
## Syntaxe  
  
```cpp  
public ref class NotImplementedException : COMException,    IException,    IPrintable,    IEquatable  
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