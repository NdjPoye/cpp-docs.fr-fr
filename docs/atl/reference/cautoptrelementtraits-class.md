---
title: "CAutoPtrElementTraits Class | Microsoft Docs"
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
  - "ATL.CAutoPtrElementTraits"
  - "CAutoPtrElementTraits"
  - "ATL::CAutoPtrElementTraits<T>"
  - "ATL.CAutoPtrElementTraits<T>"
  - "ATL::CAutoPtrElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoPtrElementTraits class"
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAutoPtrElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes, des fonctions static, et les typedefs utiles pour créer des collections de pointeurs intelligents.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template<  
typename T  
>  
class CAutoPtrElementTraits : public CDefaultElementTraits<  
ATL::CAutoPtr< T>  
>  
```  
  
#### Paramètres  
 `T`  
 Le type pointeur.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAutoPtrElementTraits::INARGTYPE](../Topic/CAutoPtrElementTraits::INARGTYPE.md)|Le type de données à utiliser pour ajouter des éléments à l'objet de classe de collection.|  
|[CAutoPtrElementTraits::OUTARGTYPE](../Topic/CAutoPtrElementTraits::OUTARGTYPE.md)|Le type de données à utiliser pour récupérer des éléments de l'objet de classe de collection.|  
  
## Notes  
 Cette classe fournit des méthodes, des fonctions static, et les typedefs pour faciliter la création des objets de classe de collection contenant les pointeurs intelligents.  Les classes [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) et [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) dérivent d' `CAutoPtrElementTraits`.  Si vous générez une collection de pointeurs intelligents qui requiert nouveau vectorielles et des opérateurs delete, utilisez [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) à la place.  
  
## Hiérarchie d'héritage  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoPtrElementTraits`  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [CDefaultElementTraits Class](../../atl/reference/cdefaultelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)