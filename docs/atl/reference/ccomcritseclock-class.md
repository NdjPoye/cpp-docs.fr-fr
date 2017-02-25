---
title: "CComCritSecLock Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComCritSecLock"
  - "ATL.CComCritSecLock<TLock>"
  - "ATL::CComCritSecLock<TLock>"
  - "ATL.CComCritSecLock"
  - "CComCritSecLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCritSecLock class"
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComCritSecLock Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour verrouiller et déverrouiller un objet de section critique.  
  
## Syntaxe  
  
```  
  
      template<  
   class TLock  
> class CComCritSecLock  
```  
  
#### Paramètres  
 *TLock*  
 l'objet à verrouiller et être déverrouillé.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCritSecLock::CComCritSecLock](../Topic/CComCritSecLock::CComCritSecLock.md)|Constructeur.|  
|[CComCritSecLock::~CComCritSecLock](../Topic/CComCritSecLock::~CComCritSecLock.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCritSecLock::Lock](../Topic/CComCritSecLock::Lock.md)|Appelez cette méthode pour verrouiller l'objet de section critique.|  
|[CComCritSecLock::Unlock](../Topic/CComCritSecLock::Unlock.md)|Appelez cette méthode pour déverrouiller l'objet de section critique.|  
  
## Notes  
 Utilisez cette classe pour verrouiller et déverrouiller des objets d'un moyen plus sûr qu'avec [classe de CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) ou [classe de CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [CComCriticalSection Class](../../atl/reference/ccomcriticalsection-class.md)   
 [CComAutoCriticalSection Class](../../atl/reference/ccomautocriticalsection-class.md)