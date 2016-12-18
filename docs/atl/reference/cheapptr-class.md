---
title: "CHeapPtr Class | Microsoft Docs"
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
  - "ATL::CHeapPtr"
  - "CHeapPtr"
  - "ATL.CHeapPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtr class"
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHeapPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une classe intelligente de pointeur pour gérer des pointeurs de tas.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template<  
typename T,  
class Allocator= CCRTAllocator  
> class CHeapPtr :  
public CHeapPtrBase< T, Allocator>  
```  
  
#### Paramètres  
 `T`  
 Le type d'objet à stocker sur le tas.  
  
 `Allocator`  
 La classe d'allocation de mémoire à utiliser.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CHeapPtr::CHeapPtr](../Topic/CHeapPtr::CHeapPtr.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CHeapPtr::Allocate](../Topic/CHeapPtr::Allocate.md)|Appelez cette méthode pour allouer de la mémoire sur le tas des objets de magasin.|  
|[CHeapPtr::Reallocate](../Topic/CHeapPtr::Reallocate.md)|Appelez cette méthode pour réaffecter la mémoire sur le tas.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CHeapPtr::operator \=](../Topic/CHeapPtr::operator%20=.md)|l'opérateur d'assignation.|  
  
## Notes  
 `CHeapPtr` est dérivé de [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) et utilise par défaut des routines CRT \(dans [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)\) pour allouer et libérer de la mémoire.  La classe [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) peut être utilisée pour construire une liste avec des pointeurs de tas.  Consultez également le [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), qui utilise des routines d'allocation de mémoire COM.  
  
## Hiérarchie d'héritage  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 `CHeapPtr`  
  
## Configuration requise  
 **Header:** atlcore.h  
  
## Voir aussi  
 [CHeapPtrBase Class](../../atl/reference/cheapptrbase-class.md)   
 [CCRTAllocator Class](../../atl/reference/ccrtallocator-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)