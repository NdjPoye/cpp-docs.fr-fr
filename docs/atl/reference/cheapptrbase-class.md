---
title: "CHeapPtrBase Class | Microsoft Docs"
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
  - "ATL.CHeapPtrBase"
  - "ATL::CHeapPtrBase"
  - "CHeapPtrBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtrBase class"
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHeapPtrBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe forme la base de plusieurs classes intelligentes de pointeur du tas.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <  
class T,  
class Allocator= CCRTAllocator   
> class CHeapPtrBase  
```  
  
#### Paramètres  
 `T`  
 Le type d'objet à stocker sur le tas.  
  
 `Allocator`  
 La classe d'allocation de mémoire à utiliser.  Par défaut des routines CRT sont utilisés pour allouer et libérer de la mémoire.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CHeapPtrBase::~CHeapPtrBase](../Topic/CHeapPtrBase::~CHeapPtrBase.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CHeapPtrBase::AllocateBytes](../Topic/CHeapPtrBase::AllocateBytes.md)|Appelez cette méthode pour allouer de la mémoire.|  
|[CHeapPtrBase::Attach](../Topic/CHeapPtrBase::Attach.md)|Appelez cette méthode pour prendre la propriété d'un pointeur existant.|  
|[CHeapPtrBase::Detach](../Topic/CHeapPtrBase::Detach.md)|Appelez cette méthode pour libérer la propriété d'un pointeur.|  
|[CHeapPtrBase::Free](../Topic/CHeapPtrBase::Free.md)|Appelez cette méthode pour supprimer un objet vers lequel pointe `CHeapPtrBase`.|  
|[CHeapPtrBase::ReallocateBytes](../Topic/CHeapPtrBase::ReallocateBytes.md)|Appelez cette méthode pour réaffecter la mémoire.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CHeapPtrBase::operator T\*](../Topic/CHeapPtrBase::operator%20T*.md)|l'opérateur de cast.|  
|[CHeapPtrBase::operator &](../Topic/CHeapPtrBase::operator%20&.md)|Et opérateur.|  
|[CHeapPtrBase::operator \-\>](../Topic/CHeapPtrBase::operator%20-%3E.md)|L'opérateur de pointeur vers membre.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CHeapPtrBase::m\_pData](../Topic/CHeapPtrBase::m_pData.md)|La variable de membre de pointeur.|  
  
## Notes  
 Cette classe forme la base de plusieurs classes intelligentes de pointeur du tas.  Les classes dérivées, par exemple, [CHeapPtr](../../atl/reference/cheapptr-class.md) et [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), ajoutez leurs propres constructeurs et opérateurs.  Consultez ces classes pour obtenir des exemples d'implémentation.  
  
## Configuration requise  
 **Header:** atlcore.h  
  
## Voir aussi  
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CComHeapPtr Class](../../atl/reference/ccomheapptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)