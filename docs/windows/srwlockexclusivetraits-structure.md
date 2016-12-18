---
title: "SRWLockExclusiveTraits, structure | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SRWLockExclusiveTraits (structure)"
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SRWLockExclusiveTraits, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit les caractéristiques communes de la classe SRWLock en mode de verrouillage exclusif.  
  
## Syntaxe  
  
```  
struct SRWLockExclusiveTraits;  
```  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`Type`|Synonyme d'un pointeur vers la classe [SRWLOCK](../windows/srwlock-class.md).|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[SRWLockExclusiveTraits::GetInvalidValue, méthode](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|Récupère un objet SRWLockExclusiveTraits qui est toujours non valide.|  
|[SRWLockExclusiveTraits::Unlock, méthode](../windows/srwlockexclusivetraits-unlock-method.md)|Libère le contrôle exclusif de l'objet SRWLock spécifié.|  
  
## Hiérarchie d'héritage  
 `SRWLockExclusiveTraits`  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::HandleTraits  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers::HandleTraits, espace de noms](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)