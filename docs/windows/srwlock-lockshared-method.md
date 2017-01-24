---
title: "SRWLock::LockShared, m&#233;thode | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LockShared (méthode)"
ms.assetid: 9d826a5c-b6a2-4430-ac85-d5753cbca889
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SRWLock::LockShared, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient un objet SRWLock en mode partagé.  
  
## Syntaxe  
  
```  
SyncLockShared LockShared();  
  
static SyncLockShared LockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### Paramètres  
 `lock`  
 Pointeur vers un objet SRWLock.  
  
## Valeur de retour  
 Un objet SRWLock en mode partagé.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [SRWLock, classe](../windows/srwlock-class.md)