---
title: "CComAutoCriticalSection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComAutoCriticalSection"
  - "ATL::CComAutoCriticalSection"
  - "CComAutoCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAutoCriticalSection class"
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComAutoCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComAutoCriticalSection` fournit des méthodes pour obtenir et libérer la propriété d'un objet de section critique.  
  
## Syntaxe  
  
```  
  
class CComAutoCriticalSection : public CComCriticalSection  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComAutoCriticalSection::CComAutoCriticalSection](../Topic/CComAutoCriticalSection::CComAutoCriticalSection.md)|Constructeur.|  
|[CComAutoCriticalSection::~CComAutoCriticalSection](../Topic/CComAutoCriticalSection::~CComAutoCriticalSection.md)|Le destructeur.|  
  
## Notes  
 `CComAutoCriticalSection` est semblable pour classer [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md), à moins qu' `CComAutoCriticalSection` lance automatiquement l'objet de section critique dans le constructeur.  
  
 En général, vous utilisez `CComAutoCriticalSection` via le nom [AutoCriticalSection](../Topic/CComMultiThreadModel::AutoCriticalSection.md)d' `typedef` .  Références de ce nom `CComAutoCriticalSection` lorsque [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) est utilisé.  
  
 Les méthodes d' `Init` et d' `Term` de [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) sont pas disponibles lors de l'utilisation de cette classe.  
  
## Hiérarchie d'héritage  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComAutoCriticalSection`  
  
## Configuration requise  
 **Header:** atlcore.h  
  
## Voir aussi  
 [CComFakeCriticalSection Class](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComCriticalSection Class](../../atl/reference/ccomcriticalsection-class.md)