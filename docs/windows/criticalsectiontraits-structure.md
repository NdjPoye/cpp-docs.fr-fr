---
title: "CriticalSectionTraits, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CriticalSectionTraits (structure)"
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CriticalSectionTraits, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécialise un objet CriticalSection pour prendre en charge soit une section critique non valide, soit une fonction pour libérer une section critique.  
  
## Syntaxe  
  
```  
struct CriticalSectionTraits;  
```  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`Type`|Un `typedef` qui définit un pointeur vers une section critique.  `Type` est défini comme `typedef CRITICAL_SECTION* Type;`.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[CriticalSectionTraits::GetInvalidValue, méthode](../windows/criticalsectiontraits-getinvalidvalue-method.md)|Spécialise un modèle CriticalSection afin que le modèle soit toujours non valide.|  
|[CriticalSectionTraits::Unlock, méthode](../windows/criticalsectiontraits-unlock-method.md)|Spécialise un modèle CriticalSection afin qu'il prenne en charge la libération de la propriété de l'objet de section critique spécifié.|  
  
## Hiérarchie d'héritage  
 `CriticalSectionTraits`  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::HandleTraits  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers::HandleTraits, espace de noms](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)