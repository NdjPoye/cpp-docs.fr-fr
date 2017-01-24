---
title: "SRWLockExclusiveTraits::Unlock, m&#233;thode | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unlock (méthode)"
ms.assetid: 7fd6b0fb-8b88-4a43-aa74-0d7fe47a0da6
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SRWLockExclusiveTraits::Unlock, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Libère le contrôle exclusif de l'objet SRWLock spécifié.  
  
## Syntaxe  
  
```  
inline static void Unlock(  
   _In_ Type srwlock  
);  
```  
  
#### Paramètres  
 `srwlock`  
 Handle vers un objet SRWLock.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::HandleTraits  
  
## Voir aussi  
 [SRWLockExclusiveTraits, structure](../windows/srwlockexclusivetraits-structure.md)