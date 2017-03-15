---
title: "SyncLockWithStatusT::SyncLockWithStatusT, constructeur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockWithStatusT, constructeur"
ms.assetid: 5d2fb820-ae1b-495f-8084-ebb4fecc3104
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# SyncLockWithStatusT::SyncLockWithStatusT, constructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
SyncLockWithStatusT(  
   _Inout_ SyncLockWithStatusT&& other  
);  
  
explicit SyncLockWithStatusT(  
   typename SyncTraits::Type sync,  
   DWORD status  
);  
```  
  
#### Paramètres  
 `other`  
 Une référence rvalue à un autre objet SyncLockWithStatusT.  
  
 `sync`  
 Une référence à un autre objet SyncLockWithStatusT.  
  
 `status`  
 La valeur de la donnée membre [status\_](../windows/synclockwithstatust-status-data-member.md) du paramètre `other` ou du paramètre `sync`.  
  
## Remarques  
 Initialise une nouvelle instance de la classe SyncLockWithStatusT.  
  
 Le premier constructeur initialise l'objet SyncLockWithStatusT actuel à partir d'un autre objet SyncLockWithStatusT spécifié par le paramètre `other`, puis invalide l'autre objet SyncLockWithStatusT.  Le deuxième constructeur est `protected`, et initialise l'objet SyncLockWithStatusT actuel à un état non valide.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::Details  
  
## Voir aussi  
 [SyncLockWithStatusT, classe](../windows/synclockwithstatust-class.md)   
 [SyncLockWithStatusT::GetStatus, méthode](../windows/synclockwithstatust-getstatus-method.md)