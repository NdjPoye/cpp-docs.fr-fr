---
title: "CCRTHeap Class | Microsoft Docs"
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
  - "ATL::CCRTHeap"
  - "ATL.CCRTHeap"
  - "CCRTHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCRTHeap class"
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCRTHeap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) à l'aide de les fonctions de tas CRT.  
  
## Syntaxe  
  
```  
  
class CCRTHeap : public IAtlMemMgr  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CCRTHeap::Allocate](../Topic/CCRTHeap::Allocate.md)|Appelez cette méthode pour allouer un bloc de mémoire.|  
|[CCRTHeap::Free](../Topic/CCRTHeap::Free.md)|Appelez cette méthode pour libérer un bloc de mémoire alloué par ce gestionnaire de mémoire.|  
|[CCRTHeap::GetSize](../Topic/CCRTHeap::GetSize.md)|Appelez cette méthode pour obtenir la taille allouée d'un bloc de mémoire alloué par ce gestionnaire de mémoire.|  
|[CCRTHeap::Reallocate](../Topic/CCRTHeap::Reallocate.md)|Appelez cette méthode pour réaffecter la mémoire allouée par ce gestionnaire de mémoire.|  
  
## Notes  
 Les fonctions d'allocation de mémoire d' outils d'`CCRTHeap` l'utilisation du tas CRT fonctionne, y compris [malloc](../../c-runtime-library/reference/malloc.md), [inscription](../../c-runtime-library/reference/free.md), [realloc](../../c-runtime-library/reference/realloc.md), et [\_msize](../../c-runtime-library/reference/msize.md).  
  
## Exemple  
 Consultez l'exemple pour [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## Hiérarchie d'héritage  
 `IAtlMemMgr`  
  
 `CCRTHeap`  
  
## Configuration requise  
 **Header:** atlmem.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComHeap Class](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap Class](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap Class](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)