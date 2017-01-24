---
title: "CHeapPtrList Class | Microsoft Docs"
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
  - "ATL::CHeapPtrList"
  - "CHeapPtrList"
  - "ATL.CHeapPtrList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtrList class"
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHeapPtrList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes utiles lorsque vous construisez une liste des pointeurs de tas.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template<  
typename E,  
class Allocator = ATL::CCRTAllocator  
>  
class CHeapPtrList : public CAtlList<  
ATL::CHeapPtr< E, Allocator>,  
CHeapPtrElementTraits< E, Allocator>  
>  
```  
  
#### Paramètres  
 `E`  
 Le type d'objet à stocker dans la classe de collection.  
  
 `Allocator`  
 La classe d'allocation de mémoire à utiliser.  La valeur par défaut est [CCRTAllocator](../../atl/reference/ccrtallocator-class.md).  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CHeapPtrList::CHeapPtrList](../Topic/CHeapPtrList::CHeapPtrList.md)|Constructeur.|  
  
## Notes  
 Cette classe fournit un constructeur et dérive des méthodes de [CAtlList](../../atl/reference/catllist-class.md) et de [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md) pour faciliter la création d'un objet de classe de collection enregistrant des pointeurs de tas.  
  
## Hiérarchie d'héritage  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CHeapPtrList`  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [CAtlList Class](../../atl/reference/catllist-class.md)   
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrElementTraits Class](../../atl/reference/cheapptrelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)