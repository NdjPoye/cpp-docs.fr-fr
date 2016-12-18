---
title: "CLocalHeap Class | Microsoft Docs"
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
  - "ATL.CLocalHeap"
  - "ATL::CLocalHeap"
  - "CLocalHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLocalHeap class"
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CLocalHeap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) à l'aide de les fonctions locales de tas Win32.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CLocalHeap : public IAtlMemMgr  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CLocalHeap::Allocate](../Topic/CLocalHeap::Allocate.md)|Appelez cette méthode pour allouer un bloc de mémoire.|  
|[CLocalHeap::Free](../Topic/CLocalHeap::Free.md)|Appelez cette méthode pour libérer un bloc de mémoire alloué par ce gestionnaire de mémoire.|  
|[CLocalHeap::GetSize](../Topic/CLocalHeap::GetSize.md)|Appelez cette méthode pour obtenir la taille allouée d'un bloc de mémoire alloué par ce gestionnaire de mémoire.|  
|[CLocalHeap::Reallocate](../Topic/CLocalHeap::Reallocate.md)|Appelez cette méthode pour réaffecter la mémoire allouée par ce gestionnaire de mémoire.|  
  
## Notes  
 Les fonctions d'allocation de mémoire d' outils d'`CLocalHeap` l'utilisation du tas local Win32 s'exécute.  
  
> [!NOTE]
>  Les fonctions locales de tas sont plus lentes que d'autres fonctions de gestion de la mémoire et ne fournissent pas autant de fonctionnalités.  Par conséquent, les nouvelles applications doivent utiliser [fonctions du tas](http://msdn.microsoft.com/library/windows/desktop/aa366711).  Ce sont disponibles dans la classe de [CWin32Heap](../../atl/reference/cwin32heap-class.md) .  
  
## Exemple  
 Consultez l'exemple pour [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## Hiérarchie d'héritage  
 `IAtlMemMgr`  
  
 `CLocalHeap`  
  
## Configuration requise  
 **Header:** atlmem.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComHeap Class](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap Class](../../atl/reference/cwin32heap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap Class](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)