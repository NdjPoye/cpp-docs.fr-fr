---
title: "SRWLock::TryLockExclusive, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryLockExclusive (méthode)"
ms.assetid: 661e8b19-3058-4511-8742-c9fbb90412c7
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SRWLock::TryLockExclusive, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Essaie d'acquérir un objet SRWLock en mode exclusif pour l'objet SRWLock actuel ou spécifié.  Si l'appel est effectué, le thread appelant devient propriétaire du verrou.  
  
## Syntaxe  
  
```  
SyncLockExclusive TryLockExclusive();  
  
static SyncLockExclusive TryLockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### Paramètres  
 `lock`  
 Pointeur vers un objet SRWLock.  
  
## Valeur de retour  
 En cas de réussite, un objet SRWLock en mode exclusif et le thread appelant prend possession du verrou.  Sinon, un objet SRWLock dont l'état est incorrect.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [SRWLock, classe](../windows/srwlock-class.md)