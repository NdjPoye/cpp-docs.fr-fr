---
title: "CComCriticalSection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComCriticalSection"
  - "CComCriticalSection"
  - "ATL::CComCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCriticalSection class"
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour obtenir et libérer la propriété d'un objet de section critique.  
  
## Syntaxe  
  
```  
  
class CComCriticalSection  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCriticalSection::CComCriticalSection](../Topic/CComCriticalSection::CComCriticalSection.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCriticalSection::Init](../Topic/CComCriticalSection::Init.md)|Crée et initialise un objet de section critique.|  
|[CComCriticalSection::Lock](../Topic/CComCriticalSection::Lock.md)|Obtient la propriété de l'objet de section critique.|  
|[CComCriticalSection::Term](../Topic/CComCriticalSection::Term.md)|Libère des ressources système utilisées par l'objet de section critique.|  
|[CComCriticalSection::Unlock](../Topic/CComCriticalSection::Unlock.md)|Libère la propriété de l'objet de section critique.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCriticalSection::m\_sec](../Topic/CComCriticalSection::m_sec.md)|Un objet de **CRITICAL\_SECTION** .|  
  
## Notes  
 `CComCriticalSection` est semblable pour classer [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md), mais que vous devez explicitement initialiser et publier la section critique.  
  
 En général, vous utilisez `CComCriticalSection` via le nom [CriticalSection](../Topic/CComMultiThreadModel::CriticalSection.md)d' `typedef` .  Références de ce nom `CComCriticalSection` lorsque [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) est utilisé.  
  
 Consultez [classe de CComCritSecLock](../../atl/reference/ccomcritseclock-class.md) pour qu'un moyen plus sûr utilise cette classe que l'appel `Lock` et `Unlock` directement.  
  
## Configuration requise  
 **Header:** atlcore.h  
  
## Voir aussi  
 [CComFakeCriticalSection Class](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComCritSecLock Class](../../atl/reference/ccomcritseclock-class.md)