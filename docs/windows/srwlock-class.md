---
title: "SRWLock, classe | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SRWLock (classe)"
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SRWLock, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un verrou de lecture\/écriture mince.  
  
## Syntaxe  
  
```  
class SRWLock;  
```  
  
## Remarques  
 Un verrou de lecture\/écriture mince est utilisé pour synchroniser l'accès entre plusieurs threads à un objet ou à une ressource.  Pour plus d'informations sur la synchronisation, consultez les [Fonctions de synchronization](http://msdn.microsoft.com/fr-fr/9b6359c2-0113-49b6-83d0-316ad95aba1b) dans la bibliothèque MSDN.  
  
## Membres  
  
### Typedefs publics  
  
|||  
|-|-|  
|**SyncLockExclusive**|Synonyme d'un objet SRWLock obtenu en mode exclusif.|  
|**SyncLockShared**|Synonyme d'un objet SRWLock obtenu en mode partagé.|  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[SRWLock::SRWLock, constructeur](../windows/srwlock-srwlock-constructor.md)|Initialise une nouvelle instance de la classe SRWLock.|  
|[SRWLock::~SRWLock, destructeur](../windows/srwlock-tilde-srwlock-destructor.md)|Libère une instance de la classe SRWLock.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[SRWLock::LockExclusive, méthode](../windows/srwlock-lockexclusive-method.md)|Obtient un objet SRWLock en mode exclusif.|  
|[SRWLock::LockShared, méthode](../windows/srwlock-lockshared-method.md)|Obtient un objet SRWLock en mode partagé.|  
|[SRWLock::TryLockExclusive, méthode](../windows/srwlock-trylockexclusive-method.md)|Essaie d'acquérir un objet SRWLock en mode exclusif pour l'objet SRWLock actuel ou spécifié.|  
|[SRWLock::TryLockShared, méthode](../windows/srwlock-trylockshared-method.md)|Essaie d'acquérir un objet SRWLock en mode partagé pour l'objet SRWLock actuel ou spécifié.|  
  
### Donnée membre protégée  
  
|Name|Description|  
|----------|-----------------|  
|[SRWLock::SRWLock\_, données de membre](../windows/srwlock-srwlock-data-member.md)|Contient la variable de verrou sous\-jacente de l'objet SRWLock actuel.|  
  
## Hiérarchie d'héritage  
 `SRWLock`  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers, espace de noms](../windows/microsoft-wrl-wrappers-namespace.md)