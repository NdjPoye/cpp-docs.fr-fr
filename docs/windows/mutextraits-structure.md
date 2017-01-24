---
title: "MutexTraits, structure | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MutexTraits (structure)"
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MutexTraits, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les caractéristiques communes de la classe [Mutex](../windows/mutex-class1.md).  
  
## Syntaxe  
  
```  
struct MutexTraits : HANDLENullTraits;  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[MutexTraits::Unlock, méthode](../windows/mutextraits-unlock-method.md)|Libère le contrôle exclusif d'une ressource partagée.|  
  
## Hiérarchie d'héritage  
 `HANDLENullTraits`  
  
 `MutexTraits`  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::HandleTraits  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers::HandleTraits, espace de noms](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)