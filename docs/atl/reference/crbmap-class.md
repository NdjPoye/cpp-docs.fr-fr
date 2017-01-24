---
title: "CRBMap Class | Microsoft Docs"
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
  - "ATL.CRBMap"
  - "CRBMap"
  - "ATL::CRBMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRBMap class"
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRBMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente une structure de mappage, à l'aide d'un arbre binaire de Rouge\- Noir.  
  
## Syntaxe  
  
```  
  
      template<   
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >   
> class CRBMap : public CRBTree< K, V, KTraits, VTraits >  
```  
  
#### Paramètres  
 `K`  
 Le type d'élément clé.  
  
 *V*  
 Le type d'élément de valeur.  
  
 `KTraits`  
 Le code utilisé pour copier ou déplacer des éléments clé.  Consultez [classe de CElementTraits](../../atl/reference/celementtraits-class.md) pour plus de détails.  
  
 `VTraits`  
 Le code utilisé pour copier ou déplacer des éléments de valeur.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CRBMap::CRBMap](../Topic/CRBMap::CRBMap.md)|Constructeur.|  
|[CRBMap::~CRBMap](../Topic/CRBMap::~CRBMap.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRBMap::Lookup](../Topic/CRBMap::Lookup.md)|Appelez cette méthode à des clés ou des valeurs de recherche dans l'objet d' `CRBMap` .|  
|[CRBMap::RemoveKey](../Topic/CRBMap::RemoveKey.md)|Appelez cette méthode pour supprimer un élément de l'objet d' `CRBMap` , vu la clé.|  
|[CRBMap::SetAt](../Topic/CRBMap::SetAt.md)|Appelez cette méthode pour insérer une paire d'éléments dans le mappage.|  
  
## Notes  
 `CRBMap` fournit la prise en charge d'un tableau de mappage d'un type donné, la gestion d'un tableau ordonné d'éléments clés et leurs valeurs associées.  Chaque clé ne peut avoir qu'une valeur associée.  Les éléments \(composée d'une clé et une valeur\) sont stockés dans une structure d'arborescence binaire, à l'aide de la méthode de [CRBMap::SetAt](../Topic/CRBMap::SetAt.md) .  Les éléments peuvent être supprimés à l'aide de la méthode de [CRBMap::RemoveKey](../Topic/CRBMap::RemoveKey.md) , qui supprime l'élément avec la valeur de clé donnée.  
  
 Parcourir l'arborescence est rendu possible avec des méthodes telles que [CRBTree::GetHeadPosition](../Topic/CRBTree::GetHeadPosition.md), [CRBTree::GetNext](../Topic/CRBTree::GetNext.md), et [CRBTree::GetNextValue](../Topic/CRBTree::GetNextValue.md).  
  
 Les paramètres d' `KTraits` et d' `VTraits` sont des classes Ctraits qui contiennent un code supplémentaire nécessaire pour copier ou déplacer des éléments.  
  
 `CRBMap` est dérivé de [CRBTree](../../atl/reference/crbtree-class.md), qui implémente un arbre binaire à l'aide de Rouge\- Noir.  [CRBMultiMap](../../atl/reference/crbmultimap-class.md) est une variante qui permet de plusieurs valeurs pour chaque clé.  Il est aussi dérivé d' `CRBTree`, et donc les partages de nombreuses fonctionnalités avec `CRBMap`.  
  
 Une alternative aux deux `CRBMap` et `CRBMultiMap` est offertes par la classe de [CAtlMap](../../atl/reference/catlmap-class.md) .  Lorsque seul un petit nombre d'éléments doit être enregistrés, utilisez la classe de [CSimpleMap](../../atl/reference/csimplemap-class.md) à la place.  
  
 Pour une description plus complet des classes de collection et leurs caractéristiques de fonctionnalités et performances, consultez [Classes de collection ATL](../../atl/atl-collection-classes.md).  
  
## Hiérarchie d'héritage  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMap`  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [CRBTree Class](../../atl/reference/crbtree-class.md)   
 [CAtlMap Class](../../atl/reference/catlmap-class.md)   
 [CRBMultiMap Class](../../atl/reference/crbmultimap-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)