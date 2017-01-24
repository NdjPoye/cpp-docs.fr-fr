---
title: "CriticalSection, classe | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CriticalSection (classe)"
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CriticalSection, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un objet de section critique.  
  
## Syntaxe  
  
```  
class CriticalSection;  
```  
  
## Membres  
  
### Constructeur  
  
|Name|Description|  
|----------|-----------------|  
|[CriticalSection::CriticalSection, constructeur](../windows/criticalsection-criticalsection-constructor.md)|Initialise un objet de synchronisation semblable à un objet de mutex, mais peut être utilisé uniquement par les threads d'un processus unique.|  
|[CriticalSection::~CriticalSection, destructeur](../windows/criticalsection-tilde-criticalsection-destructor.md)|Libère et détruit l'objet CriticalSection actuel.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[CriticalSection::TryLock, méthode](../windows/criticalsection-trylock-method.md)|Essaie d'entrer dans une section critique sans se bloquer.  Si l'appel est effectué, le thread appelant devient propriétaire de la section critique.|  
|[CriticalSection::Lock, méthode](../windows/criticalsection-lock-method.md)|Attend la propriété de l'objet de la section critique spécifié.  La fonction retourne lorsque le thread appelant reçoit la propriété.|  
|[CriticalSection::IsValid, méthode](../windows/criticalsection-isvalid-method.md)|Indique si la section critique actuelle est valide.|  
  
### Données membres protégées  
  
|Name|Description|  
|----------|-----------------|  
|[CriticalSection::cs\_, données de membre](../windows/criticalsection-cs-data-member.md)|Déclare une donnée membre de section critique.|  
  
## Hiérarchie d'héritage  
 `CriticalSection`  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers, espace de noms](../windows/microsoft-wrl-wrappers-namespace.md)