---
title: "Platform::AccessDeniedException, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::AccessDeniedException"
  - "Platform/Platform::AccessDeniedException::AccessDeniedException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::AccessDeniedException"
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::AccessDeniedException, classe
Levée lorsque l'accès à une ressource ou à une fonctionnalité est refusé.  
  
## Syntaxe  
  
```cpp  
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable  
```  
  
## Notes  
 Si vous rencontrez cette exception, vérifiez que vous avez demandé la fonctionnalité appropriée et que avez effectué les déclarations requises dans le manifeste de package de votre application. Pour plus d'informations, consultez [Configurer un package d'application Windows 8.1 à l'aide du concepteur de manifeste](../Topic/Configure%20a%20Windows%208.1%20app%20package%20by%20using%20the%20manifest%20designer.md) et la classe [COMException](../cppcx/platform-comexception-class.md).  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Platform::COMException \(classe\)](../cppcx/platform-comexception-class.md)