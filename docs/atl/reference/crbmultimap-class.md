---
title: "CRBMultiMap Class | Microsoft Docs"
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
  - "CRBMultiMap"
  - "ATL.CRBMultiMap"
  - "ATL::CRBMultiMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRBMultiMap class"
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRBMultiMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente une structure de mappage qui permet à chaque clé peut être associé à plusieurs valeurs, à l'aide d'un arbre binaire de Rouge\- Noir.  
  
## Syntaxe  
  
```  
  
      template<  
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >  
> class CRBMultiMap : public CRBTree< K, V, KTraits, VTraits >  
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
|[CRBMultiMap::CRBMultiMap](../Topic/CRBMultiMap::CRBMultiMap.md)|Constructeur.|  
|[CRBMultiMap::~CRBMultiMap](../Topic/CRBMultiMap::~CRBMultiMap.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRBMultiMap::FindFirstWithKey](../Topic/CRBMultiMap::FindFirstWithKey.md)|Appelez cette méthode pour rechercher la position du premier élément avec une clé donnée.|  
|[CRBMultiMap::GetNextValueWithKey](../Topic/CRBMultiMap::GetNextValueWithKey.md)|Appelez cette méthode pour obtenir la valeur associée à une clé donnée, puis mettez à jour la valeur de position.|  
|[CRBMultiMap::GetNextWithKey](../Topic/CRBMultiMap::GetNextWithKey.md)|Appelez cette méthode pour obtenir l'élément associé à une clé donnée, puis mettez à jour la valeur de position.|  
|[CRBMultiMap::Insert](../Topic/CRBMultiMap::Insert.md)|Appelez cette méthode pour insérer une paire d'éléments dans le mappage.|  
|[CRBMultiMap::RemoveKey](../Topic/CRBMultiMap::RemoveKey.md)|Appelez cette méthode pour supprimer tous les éléments de clé\/valeur d'une clé donnée.|  
  
## Notes  
 `CRBMultiMap` fournit la prise en charge d'un tableau de mappage d'un type donné, la gestion d'un tableau ordonné d'éléments clés et de valeurs.  Contrairement à la classe de [CRBMap](../../atl/reference/crbmap-class.md) , chaque clé peut être associé à plusieurs valeurs.  
  
 Les éléments \(composée d'une clé et une valeur\) sont stockés dans une structure d'arborescence binaire, à l'aide de la méthode de [CRBMultiMap::Insert](../Topic/CRBMultiMap::Insert.md) .  Les éléments peuvent être supprimés à l'aide de la méthode de [CRBMultiMap::RemoveKey](../Topic/CRBMultiMap::RemoveKey.md) , qui supprime tous les éléments qui correspondent à la clé spécifiée.  
  
 Parcourir l'arborescence est rendu possible avec des méthodes telles que [CRBTree::GetHeadPosition](../Topic/CRBTree::GetHeadPosition.md), [CRBTree::GetNext](../Topic/CRBTree::GetNext.md), et [CRBTree::GetNextValue](../Topic/CRBTree::GetNextValue.md).  L'accès aux valeurs de plusieurs par clé est possible de les méthodes de [CRBMultiMap::FindFirstWithKey](../Topic/CRBMultiMap::FindFirstWithKey.md), de [CRBMultiMap::GetNextValueWithKey](../Topic/CRBMultiMap::GetNextValueWithKey.md), et de [CRBMultiMap::GetNextWithKey](../Topic/CRBMultiMap::GetNextWithKey.md) .  Consultez l'exemple pour [CRBMultiMap::CRBMultiMap](../Topic/CRBMultiMap::CRBMultiMap.md) pour une illustration de cette pratique.  
  
 Les paramètres d' `KTraits` et d' `VTraits` sont des classes Ctraits qui contiennent un code supplémentaire nécessaire pour copier ou déplacer des éléments.  
  
 `CRBMultiMap` est dérivé de [CRBTree](../../atl/reference/crbtree-class.md), qui implémente un arbre binaire à l'aide de Rouge\- Noir.  Une alternative à `CRBMultiMap` et à `CRBMap` est offertes par la classe de [CAtlMap](../../atl/reference/catlmap-class.md) .  Lorsque seul un petit nombre d'éléments doit être enregistrés, utilisez la classe de [CSimpleMap](../../atl/reference/csimplemap-class.md) à la place.  
  
 Pour une description plus complet des classes de collection et leurs caractéristiques de fonctionnalités et performances, consultez [Classes de collection ATL](../../atl/atl-collection-classes.md).  
  
## Hiérarchie d'héritage  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMultiMap`  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [CRBTree Class](../../atl/reference/crbtree-class.md)   
 [CAtlMap Class](../../atl/reference/catlmap-class.md)   
 [CRBMap Class](../../atl/reference/crbmap-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)