---
title: "SRWLockSharedTraits, structure | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SRWLockSharedTraits (structure)"
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SRWLockSharedTraits, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit les caractéristiques communes de la classe SRWLock en mode de verrouillage partagé.  
  
## Syntaxe  
  
```  
struct SRWLockSharedTraits;  
```  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`Type`|Synonyme d'un pointeur vers la classe [SRWLOCK](../windows/srwlock-class.md).|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[SRWLockSharedTraits::GetInvalidValue, méthode](../windows/srwlocksharedtraits-getinvalidvalue-method.md)|Récupère un objet SRWLockSharedTraits qui est toujours non valide.|  
|[SRWLockSharedTraits::Unlock, méthode](../windows/srwlocksharedtraits-unlock-method.md)|Libère le contrôle exclusif de l'objet SRWLock spécifié.|  
  
## Hiérarchie d'héritage  
 `SRWLockSharedTraits`  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::HandleTraits  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers::HandleTraits, espace de noms](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)