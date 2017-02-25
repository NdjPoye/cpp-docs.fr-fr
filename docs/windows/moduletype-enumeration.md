---
title: "ModuleType, &#233;num&#233;ration | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ModuleType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ModuleType (énumération)"
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ModuleType, &#233;num&#233;ration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie si un module doit prendre en charge un serveur in\-process ou un serveur out\-of\-process.  
  
## Syntaxe  
  
```  
enum ModuleType;  
```  
  
## Membres  
  
### Valeurs  
  
|Name|Description|  
|----------|-----------------|  
|`InProc`|Un serveur in\-process.|  
|`OutOfProc`|Un serveur out\-of\-process.|  
|`DisableCaching`|Désactive le mécanisme de mise en cache sur Module.|  
|`InProcDisableCaching`|Combinaison de `InProc` et de `DisableCaching`.|  
|`OutOfProcDisableCaching`|Combinaison de `OutOfProc` et de `DisableCaching`.|  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)