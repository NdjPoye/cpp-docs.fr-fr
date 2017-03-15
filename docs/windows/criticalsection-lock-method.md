---
title: "CriticalSection::Lock, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lock (méthode)"
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CriticalSection::Lock, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Attend la propriété de l'objet de la section critique spécifié.  La fonction retourne lorsque le thread appelant reçoit la propriété.  
  
## Syntaxe  
  
```  
SyncLock Lock();  
  
   static SyncLock Lock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### Paramètres  
 `cs`  
 Un objet de section critique spécifié par l'utilisateur.  
  
## Valeur de retour  
 Un objet de verrou pouvant être utilisé pour déverrouiller la section critique actuelle.  
  
## Remarques  
 La première fonction **Lock** affecte l'objet de section critique actuel.  La deuxième fonction **Lock** affecte une section critique spécifiée par l'utilisateur.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [CriticalSection, classe](../windows/criticalsection-class.md)