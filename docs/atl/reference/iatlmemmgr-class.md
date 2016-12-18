---
title: "IAtlMemMgr Class | Microsoft Docs"
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
  - "IAtlMemMgr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlMemMgr class"
  - "mémoire, gérer"
  - "mémoire, memory manager"
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAtlMemMgr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente l'interface à un gestionnaire de mémoire.  
  
## Syntaxe  
  
```  
  
__interface __declspec( uuid( "654F7EF5-CFDF-4df9-A450-6C6A13C622C0" )) IAtlMemMgr  
  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[Allouez](../Topic/IAtlMemMgr::Allocate.md)|Appelez cette méthode pour allouer un bloc de mémoire.|  
|[Free \(libre\)](../Topic/IAtlMemMgr::Free.md)|Appelez cette méthode pour libérer un bloc de mémoire.|  
|[GetSize](../Topic/IAtlMemMgr::GetSize.md)|Appelez cette méthode pour récupérer la taille d'un bloc de mémoire alloué.|  
|[Réaffectez](../Topic/IAtlMemMgr::Reallocate.md)|Appelez cette méthode pour réaffecter un bloc de mémoire.|  
  
## Notes  
 Cette interface est implémentée par [CComHeap](../../atl/reference/ccomheap-class.md), [CCRTHeap](../../atl/reference/ccrtheap-class.md), [CLocalHeap](../../atl/reference/clocalheap-class.md), [CGlobalHeap](../../atl/reference/cglobalheap-class.md), ou [CWin32Heap](../../atl/reference/cwin32heap-class.md).  
  
> [!NOTE]
>  Les variables locales et les fonctions globales du tas sont plus lents que d'autres fonctions de gestion de la mémoire, et ne fournissent pas autant de fonctionnalités.  Par conséquent, les nouvelles applications doivent utiliser [fonctions du tas](http://msdn.microsoft.com/library/windows/desktop/aa366711).  Ce sont disponibles dans la classe de [CWin32Heap](../../atl/reference/cwin32heap-class.md) .  
  
## Exemple  
 [!code-cpp[NVC_ATL_Utilities#94](../../atl/codesnippet/CPP/iatlmemmgr-class_1.cpp)]  
  
## Configuration requise  
 **Header:** atlmem.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)