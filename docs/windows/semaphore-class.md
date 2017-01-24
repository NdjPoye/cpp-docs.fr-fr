---
title: "Semaphore, classe | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Semaphore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Semaphore (classe)"
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Semaphore, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un objet de synchronisation qui contrôle une ressource partagée pouvant prendre en charge un nombre limité d'utilisateurs.  
  
## Syntaxe  
  
```  
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>  
```  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`SyncLock`|Un synonyme pour une classe prenant en charge les verrous synchrones.|  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[Semaphore::Semaphore, constructeur](../windows/semaphore-semaphore-constructor.md)|Initialise une nouvelle instance de la classe Semaphore.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[InvokeHelper::Invoke, méthode](../windows/invokehelper-invoke-method.md)|Appelle le gestionnaire d'événements dont la signature contient le nombre d'arguments spécifié.|  
  
### Données membres publiques  
  
|Name|Description|  
|----------|-----------------|  
|[Semaphore::Lock, méthode](../windows/semaphore-lock-method.md)|Attend que l'objet actuel, ou l'objet associé au handle spécifié, soit dans l'état signalé ou que l'intervalle de délai d'attente spécifié se soit écoulé.|  
  
### Opérateurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[Semaphore::operator\=, opérateur](../windows/semaphore-operator-assign-operator.md)|Déplace le handle spécifié d'un objet Semaphore à l'objet Semaphore actuel.|  
  
## Hiérarchie d'héritage  
 `Semaphore`  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers, espace de noms](../windows/microsoft-wrl-wrappers-namespace.md)