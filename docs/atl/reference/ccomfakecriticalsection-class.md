---
title: "CComFakeCriticalSection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComFakeCriticalSection"
  - "CComFakeCriticalSection"
  - "ATL::CComFakeCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComFakeCriticalSection class"
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComFakeCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit les mêmes méthodes que [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) mais ne fournit pas une section critique.  
  
## Syntaxe  
  
```  
  
class CComFakeCriticalSection  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComFakeCriticalSection::Init](../Topic/CComFakeCriticalSection::Init.md)|Ne fait rien étant donné qu'il n'y a aucune section critique.|  
|[CComFakeCriticalSection::Lock](../Topic/CComFakeCriticalSection::Lock.md)|Ne fait rien étant donné qu'il n'y a aucune section critique.|  
|[CComFakeCriticalSection::Term](../Topic/CComFakeCriticalSection::Term.md)|Ne fait rien étant donné qu'il n'y a aucune section critique.|  
|[CComFakeCriticalSection::Unlock](../Topic/CComFakeCriticalSection::Unlock.md)|Ne fait rien étant donné qu'il n'y a aucune section critique.|  
  
## Notes  
 `CComFakeCriticalSection` reflète les méthodes présentes dans [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).  Toutefois, `CComFakeCriticalSection` ne fournit pas une section critique ; par conséquent, ses méthodes ne font rien.  
  
 En général, vous utilisez `CComFakeCriticalSection` par un nom d' `typedef` , `AutoCriticalSection` ou `CriticalSection`.  Lorsque vous utilisez [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) ou [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), référence des deux noms d' `typedef``CComFakeCriticalSection`.  Lorsque vous utilisez [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), ils référencent [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) et `CComCriticalSection`, respectivement.  
  
## Configuration requise  
 **Header:** atlcore.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)