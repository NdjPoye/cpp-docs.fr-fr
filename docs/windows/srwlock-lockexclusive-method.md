---
title: "SRWLock::LockExclusive, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LockExclusive (méthode)"
ms.assetid: f361b672-fca6-45cc-a9b4-310cc0d23fdc
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SRWLock::LockExclusive, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient un objet SRWLock en mode exclusif.  
  
## Syntaxe  
  
```  
SyncLockExclusive LockExclusive();  
  
static SyncLockExclusive LockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### Paramètres  
 `lock`  
 Pointeur vers un objet SRWLock.  
  
## Valeur de retour  
 Un objet SRWLock en mode exclusif.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [SRWLock, classe](../windows/srwlock-class.md)