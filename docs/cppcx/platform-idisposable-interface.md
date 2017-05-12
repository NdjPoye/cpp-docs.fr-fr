---
title: "Platform::IDisposable (interface) | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IDisposable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::IDisposable (interface)"
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 2
---
# Platform::IDisposable (interface)
Utilisée pour libérer des ressources non managées.  
  
## Syntaxe  
  
```cpp  
public interface class IDisposable  
```  
  
## Attributs  
 **GuidAttribute**\(« de0cbaea\-8065\-4a45\-b196\-c9d443f9bab3 »\)  
  
 **VersionAttribute**\(NTDDI\_WIN8\)  
  
## Membres  
 L’interface IDisposable hérite de l’interface IUnknown. IDisposable a également les types de membre suivants :  
  
 **Méthodes**  
  
 L’interface IDisposable possède les méthodes suivantes.  
  
|Méthode|Description|  
|-------------|-----------------|  
|HYPERLINK "http:\/\/msdnpreview.redmond.corp.microsoft.com\/en\-us\/library\/windows\/apps\/platform.idisposable.dispose.aspx" Dispose|Utilisée pour libérer des ressources non managées.|  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform