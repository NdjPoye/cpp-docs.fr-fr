---
title: "SemaphoreTraits, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SemaphoreTraits (structure)"
ms.assetid: eddb8576-d063-409b-9201-cc87ca5d111e
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SemaphoreTraits, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les caractéristiques communes d'un objet Semaphore.  
  
## Syntaxe  
  
```  
struct SemaphoreTraits : HANDLENullTraits;  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[SemaphoreTraits::Unlock, méthode](../windows/semaphoretraits-unlock-method.md)|Libère le contrôle d'une ressource partagée.|  
  
## Hiérarchie d'héritage  
 `HANDLENullTraits`  
  
 `SemaphoreTraits`  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::HandleTraits  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers::HandleTraits, espace de noms](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)