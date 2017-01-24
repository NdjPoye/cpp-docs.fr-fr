---
title: "Mutex, classe | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Mutex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Mutex (classe)"
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mutex, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un objet de synchronisation contrôlant exclusivement une ressource partagée.  
  
## Syntaxe  
  
```  
class Mutex : public HandleT<HandleTraits::MutexTraits>  
  
```  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|**SyncLock**|Un synonyme pour une classe prenant en charge les verrous synchrones.|  
  
### Constructeur public  
  
|Name|Description|  
|----------|-----------------|  
|[Mutex::Mutex, constructeur](../windows/mutex-mutex-constructor.md)|Initialise une nouvelle instance de la classe Mutex.|  
  
### Membres publics  
  
|Name|Description|  
|----------|-----------------|  
|[Mutex::Lock, méthode](../windows/mutex-lock-method.md)|Attend que l'objet actuel, ou l'objet Mutex associé au handle spécifié, libère le mutex ou que l'intervalle de délai d'attente spécifié se soit écoulé.|  
  
### Opérateur public  
  
|Name|Description|  
|----------|-----------------|  
|[Mutex::operator\=, opérateur](../windows/mutex-operator-assign-operator.md)|Assigne \(déplace\) l'objet Mutex spécifié à l'objet Mutex actuel.|  
  
## Hiérarchie d'héritage  
 `Mutex`  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers, espace de noms](../windows/microsoft-wrl-wrappers-namespace.md)