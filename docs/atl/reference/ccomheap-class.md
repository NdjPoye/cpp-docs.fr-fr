---
title: "CComHeap Class | Microsoft Docs"
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
  - "CComHeap"
  - "ATL.CComHeap"
  - "ATL::CComHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComHeap class"
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComHeap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) à l'aide de les fonctions d'allocation de mémoire COM.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CComHeap : public IAtlMemMgr  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComHeap::Allocate](../Topic/CComHeap::Allocate.md)|Appelez cette méthode pour allouer un bloc de mémoire.|  
|[CComHeap::Free](../Topic/CComHeap::Free.md)|Appelez cette méthode pour libérer un bloc de mémoire alloué par ce gestionnaire de mémoire.|  
|[CComHeap::GetSize](../Topic/CComHeap::GetSize.md)|Appelez cette méthode pour obtenir la taille allouée d'un bloc de mémoire alloué par ce gestionnaire de mémoire.|  
|[CComHeap::Reallocate](../Topic/CComHeap::Reallocate.md)|Appelez cette méthode pour réaffecter la mémoire allouée par ce gestionnaire de mémoire.|  
  
## Notes  
 `CComHeap` implémente des fonctions d'allocation de mémoire à l'aide de les fonctions d'allocation COM, y compris [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226), et [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280).  La quantité maximale de mémoire qui peut être alloué est égal à 2147483647\) octets d' **INT\_MAX** \(.  
  
## Exemple  
 Consultez l'exemple pour [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## Hiérarchie d'héritage  
 `IAtlMemMgr`  
  
 `CComHeap`  
  
## Configuration requise  
 **Header:** ATLComMem.h  
  
## Voir aussi  
 [Exemple de DynamicConsumer](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CWin32Heap Class](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap Class](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap Class](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)