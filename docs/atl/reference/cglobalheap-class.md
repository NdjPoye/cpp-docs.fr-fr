---
title: "CGlobalHeap Class | Microsoft Docs"
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
  - "ATL.CGlobalHeap"
  - "ATL::CGlobalHeap"
  - "CGlobalHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGlobalHeap class"
ms.assetid: e348d838-3aa7-4bee-a1b3-cd000c99f834
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CGlobalHeap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) à l'aide de les fonctions globales du tas Win32.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CGlobalHeap : public IAtlMemMgr  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CGlobalHeap::Allocate](../Topic/CGlobalHeap::Allocate.md)|Appelez cette méthode pour allouer un bloc de mémoire.|  
|[CGlobalHeap::Free](../Topic/CGlobalHeap::Free.md)|Appelez cette méthode pour libérer un bloc de mémoire alloué par ce gestionnaire de mémoire.|  
|[CGlobalHeap::GetSize](../Topic/CGlobalHeap::GetSize.md)|Appelez cette méthode pour obtenir la taille allouée d'un bloc de mémoire alloué par ce gestionnaire de mémoire.|  
|[CGlobalHeap::Reallocate](../Topic/CGlobalHeap::Reallocate.md)|Appelez cette méthode pour réaffecter la mémoire allouée par ce gestionnaire de mémoire.|  
  
## Notes  
 Les fonctions d'allocation de mémoire d' outils d'`CGlobalHeap` l'utilisation du tas global Win32 s'exécute.  
  
> [!NOTE]
>  Les fonctions globales du tas sont plus lentes que d'autres fonctions de gestion de la mémoire et ne fournissent pas autant de fonctionnalités.  Par conséquent, les nouvelles applications doivent utiliser [fonctions du tas](http://msdn.microsoft.com/library/windows/desktop/aa366711).  Ce sont disponibles dans la classe de [CWin32Heap](../../atl/reference/cwin32heap-class.md) .  Les fonctions globales sont encore utilisés par DDE et le presse\-papiers s'exécute.  
  
## Exemple  
 Consultez l'exemple pour [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## Hiérarchie d'héritage  
 `IAtlMemMgr`  
  
 `CGlobalHeap`  
  
## Configuration requise  
 **Header:** atlmem.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComHeap Class](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap Class](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap Class](../../atl/reference/clocalheap-class.md)   
 [CCRTHeap Class](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)