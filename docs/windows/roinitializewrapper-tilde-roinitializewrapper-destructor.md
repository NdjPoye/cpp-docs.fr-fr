---
title: "RoInitializeWrapper::~RoInitializeWrapper, destructeur | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper"
dev_langs: 
  - "C++"
ms.assetid: afef4c1f-ffde-4cd2-8654-8de4182eb5f4
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RoInitializeWrapper::~RoInitializeWrapper, destructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Libère le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```cpp  
~RoInitializeWrapper()  
```  
  
## Remarques  
 La classe RoInitializeWrapper appelle Windows::Foundation::Uninitialize\(\).  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HandleT, classe](../windows/handlet-class.md)