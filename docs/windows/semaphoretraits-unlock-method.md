---
title: "SemaphoreTraits::Unlock, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unlock (méthode)"
ms.assetid: 4e0ea808-b70d-43f7-81ef-998c3b34e3a0
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SemaphoreTraits::Unlock, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Libère le contrôle d'une ressource partagée.  
  
## Syntaxe  
  
```  
inline static void Unlock(  
   _In_ Type h  
);  
```  
  
#### Paramètres  
 `h`  
 Handle vers un objet sémaphore.  
  
## Remarques  
 Si l'opération de débloquage échoue, Unlock\(\) émet une erreur indiquant la cause de l'échec.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::HandleTraits  
  
## Voir aussi  
 [SemaphoreTraits, structure](../windows/semaphoretraits-structure.md)