---
title: "CRBTree Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CRBTree"
  - "CRBTree"
  - "ATL::CRBTree"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRBTree class"
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CRBTree Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour créer et utiliser une arborescence de Rouge\-Noir.  
  
## Syntaxe  
  
```  
  
      template<  
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >  
> class CRBTree  
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
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CRBTree::KINARGTYPE](../Topic/CRBTree::KINARGTYPE.md)|Tapez utilisé lorsqu'une touche est passée comme argument d'entrée.|  
|[CRBTree::KOUTARGTYPE](../Topic/CRBTree::KOUTARGTYPE.md)|Tapez utilisé lorsqu'une touche est retournée comme argument de sortie.|  
|[CRBTree::VINARGTYPE](../Topic/CRBTree::VINARGTYPE.md)|Tapez utilisé lorsqu'une valeur est passée comme argument d'entrée.|  
|[CRBTree::VOUTARGTYPE](../Topic/CRBTree::VOUTARGTYPE.md)|Tapez utilisé lorsqu'une valeur est passée comme argument de sortie.|  
  
### Classes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRBTree::CPair Class](../Topic/CRBTree::CPair%20Class.md)|Une classe contenant les éléments de clés et de valeurs.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CRBTree::~CRBTree](../Topic/CRBTree::~CRBTree.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRBTree::FindFirstKeyAfter](../Topic/CRBTree::FindFirstKeyAfter.md)|Appelez cette méthode pour rechercher la position de l'élément qui utilise la clé suivante disponible.|  
|[CRBTree::GetAt](../Topic/CRBTree::GetAt.md)|Appelez cette méthode pour obtenir l'élément à une position dans l'arborescence.|  
|[CRBTree::GetCount](../Topic/CRBTree::GetCount.md)|Appelez cette méthode pour obtenir le nombre d'éléments dans l'arborescence.|  
|[CRBTree::GetHeadPosition](../Topic/CRBTree::GetHeadPosition.md)|Appelez cette méthode pour obtenir la valeur de la position de l'élément au début de l'arborescence.|  
|[CRBTree::GetKeyAt](../Topic/CRBTree::GetKeyAt.md)|Appelez cette méthode pour obtenir la clé d'une position dans l'arborescence.|  
|[CRBTree::GetNext](../Topic/CRBTree::GetNext.md)|Appelez cette méthode pour obtenir un pointeur vers un élément stocké dans l'objet d' `CRBTree` , et avancez la position à l'élément.|  
|[CRBTree::GetNextAssoc](../Topic/CRBTree::GetNextAssoc.md)|Appelez cette méthode pour obtenir la clé et la valeur d'un élément stocké dans le mappage et pour avancer la position à l'élément.|  
|[CRBTree::GetNextKey](../Topic/CRBTree::GetNextKey.md)|Appelez cette méthode pour obtenir la clé d'un élément stocké dans l'arborescence et pour avancer la position à l'élément.|  
|[CRBTree::GetNextValue](../Topic/CRBTree::GetNextValue.md)|Appelez cette méthode pour obtenir la valeur d'un élément stocké dans l'arborescence et pour avancer la position à l'élément.|  
|[CRBTree::GetPrev](../Topic/CRBTree::GetPrev.md)|Appelez cette méthode pour obtenir un pointeur vers un élément stocké dans l'objet d' `CRBTree` , puis mettez à jour la position à l'élément précédent.|  
|[CRBTree::GetTailPosition](../Topic/CRBTree::GetTailPosition.md)|Appelez cette méthode pour atteindre la valeur de position de l'élément la fin de l'arborescence.|  
|[CRBTree::GetValueAt](../Topic/CRBTree::GetValueAt.md)|Appelez cette méthode pour récupérer la valeur stockée à une position dans l'objet d' `CRBTree` .|  
|[CRBTree::IsEmpty](../Topic/CRBTree::IsEmpty.md)|Appelez cette méthode pour déterminer un objet vide d'arborescence.|  
|[CRBTree::RemoveAll](../Topic/CRBTree::RemoveAll.md)|Appelez cette méthode pour supprimer tous les éléments de l'objet de **CRBTree** .|  
|[CRBTree::RemoveAt](../Topic/CRBTree::RemoveAt.md)|Appelez cette méthode pour supprimer l'élément à la position donnée dans l'objet de **CRBTree** .|  
|[CRBTree::SetValueAt](../Topic/CRBTree::SetValueAt.md)|Appelez cette méthode pour remplacer la valeur stockée à une position dans l'objet d' `CRBTree` .|  
  
## Notes  
 Une arborescence de Rouge\- Noir est un arbre de recherche binaire qui utilise un bit supplémentaire des informations par nœud pour vérifier qu'il reste « équilibré, » autrement dit, la hauteur de l'arborescence ne développe pas de façon disproportionnée grand et n'affecte pas les performances.  
  
 Cette classe de modèle est conçue pour être utilisée par [CRBMap](../../atl/reference/crbmap-class.md) et [CRBMultiMap](../../atl/reference/crbmultimap-class.md).  La partie des méthodes qui composent ces classes dérivées sont fournies par `CRBTree`.  
  
 Pour une description plus complet des classes de collection et leurs caractéristiques de fonctionnalités et performances, consultez [Classes de collection ATL](../../atl/atl-collection-classes.md).  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)