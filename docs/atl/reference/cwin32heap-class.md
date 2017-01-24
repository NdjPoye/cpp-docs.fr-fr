---
title: "CWin32Heap Class | Microsoft Docs"
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
  - "ATL::CWin32Heap"
  - "ATL.CWin32Heap"
  - "CWin32Heap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWin32Heap class"
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWin32Heap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) à l'aide de les fonctions d'allocation du tas Win32.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CWin32Heap : public IAtlMemMgr  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWin32Heap::CWin32Heap](../Topic/CWin32Heap::CWin32Heap.md)|Constructeur.|  
|[CWin32Heap::~CWin32Heap](../Topic/CWin32Heap::~CWin32Heap.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWin32Heap::Allocate](../Topic/CWin32Heap::Allocate.md)|Alloue un bloc de mémoire de l'objet heap.|  
|[CWin32Heap::Attach](../Topic/CWin32Heap::Attach.md)|Joint l'objet heap à un tas existant.|  
|[CWin32Heap::Detach](../Topic/CWin32Heap::Detach.md)|Détache l'objet heap d'un tas existant.|  
|[CWin32Heap::Free](../Topic/CWin32Heap::Free.md)|Libère la mémoire précédemment allouée du tas.|  
|[CWin32Heap::GetSize](../Topic/CWin32Heap::GetSize.md)|Retourne la taille d'un bloc de mémoire alloué de l'objet heap.|  
|[CWin32Heap::Reallocate](../Topic/CWin32Heap::Reallocate.md)|Réaffecte un bloc de mémoire de l'objet heap.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWin32Heap::m\_bOwnHeap](../Topic/CWin32Heap::m_bOwnHeap.md)|Une balise utilisée pour déterminer la propriété actuelle du handle du tas.|  
|[CWin32Heap::m\_hHeap](../Topic/CWin32Heap::m_hHeap.md)|Handle vers l'objet heap.|  
  
## Notes  
 `CWin32Heap` implémente les méthodes d'allocation de mémoire à l'aide de les fonctions d'allocation du tas Win32, y compris [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597) et [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701).  Contrairement aux autres classes de tas, `CWin32Heap` requiert un handle valide du tas d'être fourni avant que la mémoire est allouée : les autres classes ont comme valeur par défaut à utiliser le tas de processus.  Le handle peut être fourni au constructeur ou la méthode de [CWin32Heap::Attach](../Topic/CWin32Heap::Attach.md) .  Consultez la méthode de [CWin32Heap::CWin32Heap](../Topic/CWin32Heap::CWin32Heap.md) pour plus de détails.  
  
## Exemple  
 Consultez l'exemple pour [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## Hiérarchie d'héritage  
 `IAtlMemMgr`  
  
 `CWin32Heap`  
  
## Configuration requise  
 **Header:** atlmem.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)   
 [CLocalHeap Class](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap Class](../../atl/reference/ccrtheap-class.md)   
 [CComHeap Class](../../atl/reference/ccomheap-class.md)