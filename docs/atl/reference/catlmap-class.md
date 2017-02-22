---
title: "CAtlMap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlMap"
  - "CAtlMap"
  - "ATL::CAtlMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlMap class"
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CAtlMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour créer et gérer un objet de mappage.  
  
## Syntaxe  
  
```  
  
      template<  
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >  
>  
class CAtlMap  
```  
  
#### Paramètres  
 `K`  
 Le type d'élément clé.  
  
 V  
 Le type d'élément de valeur.  
  
 `KTraits`  
 Le code utilisé pour copier ou déplacer des éléments clé.  Consultez [classe de CElementTraits](../../atl/reference/celementtraits-class.md) pour plus de détails.  
  
 `VTraits`  
 Le code utilisé pour copier ou déplacer des éléments de valeur.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlMap::KINARGTYPE](../Topic/CAtlMap::KINARGTYPE.md)|Tapez utilisé lorsqu'une touche est passée comme argument d'entrée|  
|[CAtlMap::KOUTARGTYPE](../Topic/CAtlMap::KOUTARGTYPE.md)|Tapez utilisé lorsqu'une touche est retournée comme argument de sortie.|  
|[CAtlMap::VINARGTYPE](../Topic/CAtlMap::VINARGTYPE.md)|Tapez utilisé lorsqu'une valeur est passée comme argument d'entrée.|  
|[CAtlMap::VOUTARGTYPE](../Topic/CAtlMap::VOUTARGTYPE.md)|Tapez utilisé lorsqu'une valeur est passée comme argument de sortie.|  
  
### Classes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlMap::CPair Class](../Topic/CAtlMap::CPair%20Class.md)|Une classe contenant les éléments de clés et de valeurs.|  
  
### Membres de données de CPair  
  
|Nom|Description|  
|---------|-----------------|  
|[CPair::m\_key](../Topic/CAtlMap::CPair::m_key.md)|Le membre enregistrant l'élément clé.|  
|[CPair::m\_value](../Topic/CAtlMap::CPair::m_value.md)|Le membre enregistrement de l'élément de valeur.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlMap::CAtlMap](../Topic/CAtlMap::CAtlMap.md)|Constructeur.|  
|[CAtlMap::~CAtlMap](../Topic/CAtlMap::~CAtlMap.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlMap::AssertValid](../Topic/CAtlMap::AssertValid.md)|Appelez cette méthode pour générer une `CAtlMap` ASSERT si n'est pas valide.|  
|[CAtlMap::DisableAutoRehash](../Topic/CAtlMap::DisableAutoRehash.md)|Appelez cette méthode pour désactiver le nouveau hachage automatique de l'objet d' `CAtlMap` .|  
|[CAtlMap::EnableAutoRehash](../Topic/CAtlMap::EnableAutoRehash.md)|Appelez cette méthode pour activer le nouveau hachage automatique de l'objet d' `CAtlMap` .|  
|[CAtlMap::GetAt](../Topic/CAtlMap::GetAt.md)|Appelez cette méthode pour retourner l'élément à une position spécifiée dans le mappage.|  
|[CAtlMap::GetCount](../Topic/CAtlMap::GetCount.md)|Appelez cette méthode pour récupérer le nombre d'éléments dans le mappage.|  
|[CAtlMap::GetHashTableSize](../Topic/CAtlMap::GetHashTableSize.md)|Appelez cette méthode pour déterminer le nombre de coffres dans la table de hachage du mappage.|  
|[CAtlMap::GetKeyAt](../Topic/CAtlMap::GetKeyAt.md)|Appelez cette méthode pour extraire la clé stockée à la position de l'objet d' `CAtlMap` .|  
|[CAtlMap::GetNext](../Topic/CAtlMap::GetNext.md)|Appelez cette méthode pour obtenir un pointeur vers la prochaine paire d'éléments stockée dans l'objet d' `CAtlMap` .|  
|[CAtlMap::GetNextAssoc](../Topic/CAtlMap::GetNextAssoc.md)|Obtient l'élément pour itérer.|  
|[CAtlMap::GetNextKey](../Topic/CAtlMap::GetNextKey.md)|Appelez cette méthode pour récupérer la prochaine clé de l'objet d' `CAtlMap` .|  
|[CAtlMap::GetNextValue](../Topic/CAtlMap::GetNextValue.md)|Appelez cette méthode pour obtenir la prochaine valeur de l'objet d' `CAtlMap` .|  
|[CAtlMap::GetStartPosition](../Topic/CAtlMap::GetStartPosition.md)|Appelez cette méthode pour démarrer une itération de mappage.|  
|[CAtlMap::GetValueAt](../Topic/CAtlMap::GetValueAt.md)|Appelez cette méthode pour récupérer la valeur stockée à une position dans l'objet d' `CAtlMap` .|  
|[CAtlMap::InitHashTable](../Topic/CAtlMap::InitHashTable.md)|Appelez cette méthode pour initialiser la table de hachage.|  
|[CAtlMap::IsEmpty](../Topic/CAtlMap::IsEmpty.md)|Appelez cette méthode pour déterminer un objet de mappage vide.|  
|[CAtlMap::Lookup](../Topic/CAtlMap::Lookup.md)|Appelez cette méthode à des clés ou des valeurs de recherche dans l'objet d' `CAtlMap` .|  
|[CAtlMap::Rehash](../Topic/CAtlMap::Rehash.md)|Appelez cette méthode au réchauffé l'objet d' `CAtlMap` .|  
|[CAtlMap::RemoveAll](../Topic/CAtlMap::RemoveAll.md)|Appelez cette méthode pour supprimer tous les éléments de l'objet d' `CAtlMap` .|  
|[CAtlMap::RemoveAtPos](../Topic/CAtlMap::RemoveAtPos.md)|Appelez cette méthode pour supprimer l'élément à la position de l'objet d' `CAtlMap` .|  
|[CAtlMap::RemoveKey](../Topic/CAtlMap::RemoveKey.md)|Appelez cette méthode pour supprimer un élément de l'objet d' `CAtlMap` , vu la clé.|  
|[CAtlMap::SetAt](../Topic/CAtlMap::SetAt.md)|Appelez cette méthode pour insérer une paire d'éléments dans le mappage.|  
|[CAtlMap::SetOptimalLoad](../Topic/CAtlMap::SetOptimalLoad.md)|Appelez cette méthode pour définir le chargement optimal de l'objet d' `CAtlMap` .|  
|[CAtlMap::SetValueAt](../Topic/CAtlMap::SetValueAt.md)|Appelez cette méthode pour remplacer la valeur stockée à une position dans l'objet d' `CAtlMap` .|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlMap::operator](../Topic/CAtlMap::operator.md)|Remplace et ajoute un élément à `CAtlMap`.|  
  
## Notes  
 `CAtlMap` fournit la prise en charge d'un tableau de mappage d'un type donné, la gestion d'un tableau non ordonné d'éléments clés et leurs valeurs associées.  Les éléments \(composée d'une clé et une valeur\) sont stockés à l'aide d'un algorithme de hachage, ce qui permet un grand nombre de données efficacement à stocker et être récupérées.  
  
 Les paramètres d' `KTraits` et d' `VTraits` sont des classes Ctraits qui contiennent un code supplémentaire nécessaire pour copier ou déplacer des éléments.  
  
 Une alternative à `CAtlMap` est offertes par la classe de [CRBMap](../../atl/reference/crbmap-class.md) .  `CRBMap` stocke également les paires clé\/valeur, mais caractéristiques de performance d'objets exposés différentes.  Le temps nécessaire pour insérer un élément, rechercher une clé, ou pour supprimer une clé d'un objet d' `CRBMap` est le journal de commande *\(n\)*, où *n* est le nombre d'éléments.  Pour `CAtlMap`, toutes ces opérations prennent généralement un temps fixe, bien que les pires scénarios peuvent être de la commande *N.* Par conséquent, dans un cas courant, `CAtlMap` est plus rapide.  
  
 L'autre différence entre `CRBMap` et `CAtlMap` est évidente en itérant au sein de les éléments stockés.  Dans `CRBMap`, les éléments sont suivis dans un ordre trié.  Dans `CAtlMap`, les éléments ne sont pas classés, et aucune commande ne peut être déduite.  
  
 Lorsqu'un petit nombre d'éléments doivent être enregistrés, utilisez la classe de [CSimpleMap](../../atl/reference/csimplemap-class.md) à la place.  
  
 Pour plus d'informations, consultez [Classes de collection ATL](../../atl/atl-collection-classes.md).  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [Exemple de bannière](../../top/visual-cpp-samples.md)   
 [Exemple UpdatePV](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)