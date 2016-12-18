---
title: "SyncLockT::~SyncLockT, destructeur | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~SyncLockT, destructeur"
ms.assetid: 9e14870d-017d-45fe-a3dc-cd86b6fa1c3a
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SyncLockT::~SyncLockT, destructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
~SyncLockT();  
```  
  
## Remarques  
 Libère une instance de la classe SyncLockT.  
  
 Ce destructeur déverrouille également l'instance SyncLockT actuelle.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::Details  
  
## Voir aussi  
 [SyncLockT, classe](../windows/synclockt-class.md)