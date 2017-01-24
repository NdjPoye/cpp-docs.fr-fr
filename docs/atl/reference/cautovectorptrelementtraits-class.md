---
title: "CAutoVectorPtrElementTraits Class | Microsoft Docs"
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
  - "ATL::CAutoVectorPtrElementTraits<T>"
  - "ATL.CAutoVectorPtrElementTraits"
  - "ATL.CAutoVectorPtrElementTraits<T>"
  - "ATL::CAutoVectorPtrElementTraits"
  - "CAutoVectorPtrElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoVectorPtrElementTraits class"
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAutoVectorPtrElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes, des fonctions static, et les typedefs utiles pour créer des collections de pointeurs intelligents à nouveau vectorielles et d'opérateurs delete.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template<  
typename T  
>  
class CAutoVectorPtrElementTraits : public CDefaultElementTraits<  
ATL::CAutoVectorPtr< T>  
>  
```  
  
#### Paramètres  
 `T`  
 Le type pointeur.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAutoVectorPtrElementTraits::INARGTYPE](../Topic/CAutoVectorPtrElementTraits::INARGTYPE.md)|Le type de données à utiliser pour ajouter des éléments à l'objet de classe de collection.|  
|[CAutoVectorPtrElementTraits::OUTARGTYPE](../Topic/CAutoVectorPtrElementTraits::OUTARGTYPE.md)|Le type de données à utiliser pour récupérer des éléments de l'objet de classe de collection.|  
  
## Notes  
 Cette classe fournit des méthodes, des fonctions static, et les typedefs pour faciliter la création des objets de classe de collection contenant les pointeurs intelligents.  Contrairement à [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md), cette classe utilise nouveau vectorielles et des opérateurs delete.  
  
## Hiérarchie d'héritage  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoVectorPtrElementTraits`  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [CDefaultElementTraits Class](../../atl/reference/cdefaultelementtraits-class.md)   
 [CAutoVectorPtr Class](../../atl/reference/cautovectorptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)