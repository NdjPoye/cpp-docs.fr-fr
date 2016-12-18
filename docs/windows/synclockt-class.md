---
title: "SyncLockT, classe | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockT (classe)"
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SyncLockT, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockT;  
```  
  
#### Paramètres  
 `SyncTraits`  
 Le type qui peut prendre la propriété d'une ressource.  
  
## Remarques  
 Représente un type pouvant prendre la propriété exclusive ou partagée d'une ressource.  
  
 La classe SyncLockT est utilisée, par exemple, afin d'implémenter la classe [SRWLock](../windows/srwlock-class.md).  
  
## Membres  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[SyncLockT::SyncLockT, constructeur](../windows/synclockt-synclockt-constructor.md)|Initialise une nouvelle instance de la classe SyncLockT.|  
|[SyncLockT::~SyncLockT, destructeur](../windows/synclockt-tilde-synclockt-destructor.md)|Libère une instance de la classe SyncLockT.|  
  
### Constructeurs protégés  
  
|Name|Description|  
|----------|-----------------|  
|[SyncLockT::SyncLockT, constructeur](../windows/synclockt-synclockt-constructor.md)|Initialise une nouvelle instance de la classe SyncLockT.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[SyncLockT::IsLocked, méthode](../windows/synclockt-islocked-method.md)|Indique si l'objet SyncLockT actuel possède une ressource; autrement dit, si l'objet SyncLockT est *verrouillé*.|  
|[SyncLockT::Unlock, méthode](../windows/synclockt-unlock-method.md)|Libère le contrôle de la resource détenue par l'objet SyncLockT actuel, le cas échéant.|  
  
### Données membres protégées  
  
|Name|Description|  
|----------|-----------------|  
|[SyncLockT::sync\_, données de membre](../windows/synclockt-sync-data-member.md)|Contient la ressource sous\-jacente représentée par la classe SyncLockT.|  
  
## Hiérarchie d'héritage  
 `SyncLockT`  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::Details  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers::Details, espace de noms](../windows/microsoft-wrl-wrappers-details-namespace.md)   
 [SRWLock, classe](../windows/srwlock-class.md)