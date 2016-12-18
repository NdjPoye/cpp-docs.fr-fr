---
title: "CCRTAllocator Class | Microsoft Docs"
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
  - "CCRTAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCRTAllocator class"
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCRTAllocator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour la gestion de la mémoire à des routines de mémoire CRT.  
  
## Syntaxe  
  
```  
  
class ATL::CCRTAllocator  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CCRTAllocator::Allocate](../Topic/CCRTAllocator::Allocate.md)|\(Statique\) appelez cette méthode pour allouer de la mémoire.|  
|[CCRTAllocator::Free](../Topic/CCRTAllocator::Free.md)|\(Statique\) appelez cette méthode pour libérer de la mémoire.|  
|[CCRTAllocator::Reallocate](../Topic/CCRTAllocator::Reallocate.md)|\(Statique\) appelez cette méthode pour réaffecter la mémoire.|  
  
## Notes  
 Cette classe est utilisée par [CHeapPtr](../../atl/reference/cheapptr-class.md) pour fournir des routines d'allocation de mémoire CRT.  Les homologues classe, [CComAllocator](../../atl/reference/ccomallocator-class.md), fournit les mêmes méthodes à l'aide de les routines COM.  
  
## Configuration requise  
 **Header:** atlcore.h  
  
## Voir aussi  
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CComAllocator Class](../../atl/reference/ccomallocator-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)