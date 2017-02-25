---
title: "CComAllocator Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComAllocator"
  - "ATL::CComAllocator"
  - "CComAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAllocator class"
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComAllocator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour la gestion de la mémoire à des routines de mémoire COM.  
  
## Syntaxe  
  
```  
  
class CComAllocator  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComAllocator::Allocate](../Topic/CComAllocator::Allocate.md)|Appelez cette méthode statique pour allouer de la mémoire.|  
|[CComAllocator::Free](../Topic/CComAllocator::Free.md)|Appelez cette méthode statique pour libérer la mémoire allouée.|  
|[CComAllocator::Reallocate](../Topic/CComAllocator::Reallocate.md)|Appelez cette méthode statique pour réaffecter la mémoire.|  
  
## Notes  
 Cette classe est utilisée par [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) pour fournir des routines d'allocation de mémoire COM.  Les homologues classe, [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), fournit les mêmes méthodes à l'aide de les routines CRT.  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [CComHeapPtr Class](../../atl/reference/ccomheapptr-class.md)   
 [CCRTAllocator Class](../../atl/reference/ccrtallocator-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)