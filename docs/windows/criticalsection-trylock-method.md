---
title: "CriticalSection::TryLock, m&#233;thode | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryLock (méthode)"
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CriticalSection::TryLock, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Essaie d'entrer dans une section critique sans se bloquer.  Si l'appel est effectué, le thread appelant devient propriétaire de la section critique.  
  
## Syntaxe  
  
```  
SyncLock TryLock();  
  
static SyncLock TryLock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### Paramètres  
 `cs`  
 Un objet de section critique spécifié par l'utilisateur.  
  
## Valeur de retour  
 Une valeur différente de zéro si la section critique est correctement écrite ou que le thread possède déjà une section critique.  Zéro si un autre thread possède déjà une section critique.  
  
## Remarques  
 La première fonction **TryLock** affecte l'objet de section critique actuel.  La deuxième fonction **TryLock** affecte une section critique spécifiée par l'utilisateur.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [CriticalSection, classe](../windows/criticalsection-class.md)