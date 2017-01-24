---
title: "CHeapPtrElementTraits Class | Microsoft Docs"
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
  - "ATL.CHeapPtrElementTraits"
  - "CHeapPtrElementTraits"
  - "ATL::CHeapPtrElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtrElementTraits class"
ms.assetid: 910e0e06-3c8b-4242-bf00-b57eb74fbc77
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHeapPtrElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes, des fonctions static, et les typedefs utiles pour créer des collections de pointeurs de tas.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template<  
typename T,  
class Allocator= ATL::CCRTAllocator  
>  
class CHeapPtrElementTraits : public CDefaultElementTraits<  
ATL::CHeapPtr< T, Allocator>  
>  
```  
  
#### Paramètres  
 `T`  
 Le type d'objet à stocker dans la classe de collection.  
  
 `Allocator`  
 La classe d'allocation de mémoire à utiliser.  La valeur par défaut est [CCRTAllocator](../../atl/reference/ccrtallocator-class.md).  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CHeapPtrElementTraits::INARGTYPE](../Topic/CHeapPtrElementTraits::INARGTYPE.md)|Le type de données à utiliser pour ajouter des éléments à l'objet de classe de collection.|  
|[CHeapPtrElementTraits::OUTARGTYPE](../Topic/CHeapPtrElementTraits::OUTARGTYPE.md)|Le type de données à utiliser pour récupérer des éléments de l'objet de classe de collection.|  
  
## Notes  
 Cette classe fournit des méthodes, des fonctions static, et les typedefs pour faciliter la création des objets de classe de collection contenant des pointeurs de tas.  La classe `CHeapPtrList` dérive d' `CHeapPtrElementTraits`.  
  
 Pour plus d'informations, consultez [Classes de collection ATL](../../atl/atl-collection-classes.md).  
  
## Hiérarchie d'héritage  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CHeapPtrElementTraits`  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [CDefaultElementTraits Class](../../atl/reference/cdefaultelementtraits-class.md)   
 [CComHeapPtr Class](../../atl/reference/ccomheapptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)