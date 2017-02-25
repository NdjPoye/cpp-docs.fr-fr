---
title: "SyncLockT::SyncLockT, constructeur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockT, constructeur"
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# SyncLockT::SyncLockT, constructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
SyncLockT(  
   _Inout_ SyncLockT&& other  
);  
  
explicit SyncLockT(  
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);  
```  
  
#### Paramètres  
 `other`  
 Une référence rvalue à un autre objet SyncLockT.  
  
 `sync`  
 Une référence à un autre objet SyncLockWithStatusT.  
  
## Remarques  
 Initialise une nouvelle instance de la classe SyncLockT.  
  
 Le premier constructeur initialise l'objet SyncLockT actuel à partir d'un autre objet SyncLockT spécifié par le paramètre `other`, puis invalide l'autre objet SyncLockT.  Le deuxième constructeur est `protected`, et initialise l'objet SyncLockT actuel à un état non valide.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::Details  
  
## Voir aussi  
 [SyncLockT, classe](../windows/synclockt-class.md)