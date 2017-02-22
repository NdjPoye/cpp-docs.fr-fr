---
title: "CAtlList Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlList"
  - "CAtlList"
  - "ATL::CAtlList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlList class"
ms.assetid: 09e98053-64b2-4efa-99ab-d0542caaf981
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CAtlList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour créer et gérer un objet de liste.  
  
## Syntaxe  
  
```  
  
      template<  
   typename E,  
   class ETraits = CElementTraits< E >  
>  
class CAtlList  
```  
  
#### Paramètres  
 `E`  
 Type de l'élément.  
  
 `ETraits`  
 Le code utilisé pour copier ou déplacer des éléments.  Consultez [classe de CElementTraits](../../atl/reference/celementtraits-class.md) pour plus de détails.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlList::INARGTYPE](../Topic/CAtlList::INARGTYPE.md)||  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlList::CAtlList](../Topic/CAtlList::CAtlList.md)|Constructeur.|  
|[CAtlList::~CAtlList](../Topic/CAtlList::~CAtlList.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlList::AddHead](../Topic/CAtlList::AddHead.md)|Appelez cette méthode pour ajouter un élément au début de la liste.|  
|[CAtlList::AddHeadList](../Topic/CAtlList::AddHeadList.md)|Appelez cette méthode pour ajouter une liste existante au début de la liste.|  
|[CAtlList::AddTail](../Topic/CAtlList::AddTail.md)|Appelez cette méthode pour ajouter un élément à la fin de cette liste.|  
|[CAtlList::AddTailList](../Topic/CAtlList::AddTailList.md)|Appelez cette méthode pour ajouter une liste existante à la fin de cette liste.|  
|[CAtlList::AssertValid](../Topic/CAtlList::AssertValid.md)|Appelez cette méthode pour confirmer la liste est valide.|  
|[CAtlList::Find](../Topic/CAtlList::Find.md)|Appelez cette méthode pour rechercher la liste pour l'élément spécifié.|  
|[CAtlList::FindIndex](../Topic/CAtlList::FindIndex.md)|Appelez cette méthode pour obtenir la position d'un élément, attribuée une valeur d'index.|  
|[CAtlList::GetAt](../Topic/CAtlList::GetAt.md)|Appelez cette méthode pour retourner l'élément à une position spécifiée dans la liste.|  
|[CAtlList::GetCount](../Topic/CAtlList::GetCount.md)|Appelez cette méthode pour retourner le nombre d'objets de la liste.|  
|[CAtlList::GetHead](../Topic/CAtlList::GetHead.md)|Appelez cette méthode pour retourner l'élément au début de la liste.|  
|[CAtlList::GetHeadPosition](../Topic/CAtlList::GetHeadPosition.md)|Appelez cette méthode pour obtenir la position de la tête de la liste.|  
|[CAtlList::GetNext](../Topic/CAtlList::GetNext.md)|Appelez cette méthode pour retourner l'élément de la liste.|  
|[CAtlList::GetPrev](../Topic/CAtlList::GetPrev.md)|Appelez cette méthode pour retourner l'élément précédent de la liste.|  
|[CAtlList::GetTail](../Topic/CAtlList::GetTail.md)|Appelez cette méthode pour retourner l'élément à la fin de la liste.|  
|[CAtlList::GetTailPosition](../Topic/CAtlList::GetTailPosition.md)|Appelez cette méthode pour obtenir la position de la fin de la liste.|  
|[CAtlList::InsertAfter](../Topic/CAtlList::InsertAfter.md)|Appelez cette méthode pour insérer un nouvel élément dans la liste une fois la position spécifiée.|  
|[CAtlList::InsertBefore](../Topic/CAtlList::InsertBefore.md)|Appelez cette méthode pour insérer un nouvel élément dans la liste avant la position spécifiée.|  
|[CAtlList::IsEmpty](../Topic/CAtlList::IsEmpty.md)|Appelez cette méthode pour déterminer si la liste est vide.|  
|[CAtlList::MoveToHead](../Topic/CAtlList::MoveToHead.md)|Appelez cette méthode pour déplacer l'élément spécifié au début de la liste.|  
|[CAtlList::MoveToTail](../Topic/CAtlList::MoveToTail.md)|Appelez cette méthode pour déplacer l'élément spécifié à la fin de la liste.|  
|[CAtlList::RemoveAll](../Topic/CAtlList::RemoveAll.md)|Appelez cette méthode pour supprimer tous les éléments de la liste.|  
|[CAtlList::RemoveAt](../Topic/CAtlList::RemoveAt.md)|Appelez cette méthode pour supprimer un seul élément de la liste.|  
|[CAtlList::RemoveHead](../Topic/CAtlList::RemoveHead.md)|Appelez cette méthode pour supprimer l'élément au début de la liste.|  
|[CAtlList::RemoveHeadNoReturn](../Topic/CAtlList::RemoveHeadNoReturn.md)|Appelez cette méthode pour supprimer l'élément au début de la liste sans retourner une valeur.|  
|[CAtlList::RemoveTail](../Topic/CAtlList::RemoveTail.md)|Appelez cette méthode pour supprimer l'élément à la fin de la liste.|  
|[CAtlList::RemoveTailNoReturn](../Topic/CAtlList::RemoveTailNoReturn.md)|Appelez cette méthode pour supprimer l'élément à la fin de la liste sans retourner une valeur.|  
|[CAtlList::SetAt](../Topic/CAtlList::SetAt.md)|Appelez cette méthode pour définir la valeur de l'élément à une position dans la liste.|  
|[CAtlList::SwapElements](../Topic/CAtlList::SwapElements.md)|Appelez cette méthode pour échanger des éléments dans la liste.|  
  
## Notes  
 La classe d' `CAtlList` prend en charge les listes ordonnées d'objets non uniques accessibles de manière séquentielle ou par valeur.  Les listes d'`CAtlList` se comportent comme doublement des listes liées.  Chaque liste a une début et de fin, et de nouveaux éléments \(ou listes dans certains cas\) peuvent être ajoutés à la fin de la liste, ou être inséré avant ou après les éléments spécifiques.  
  
 La plupart des méthodes d' `CAtlList` se servent d'une valeur de position.  Cette valeur est utilisée par les méthodes pour référencer l'emplacement mémoire réel dans lequel les éléments sont stockés, et ne doit pas être calculée ou attendue directement.  S'il est nécessaire d'accéder *au nième*élément dans la liste, la méthode [CAtlList::FindIndex](../Topic/CAtlList::FindIndex.md) retourne la valeur correspondante de position d'un index donné.  Les méthodes [CAtlList::GetNext](../Topic/CAtlList::GetNext.md) et [CAtlList::GetPrev](../Topic/CAtlList::GetPrev.md) peuvent être utilisées pour itérer au sein de les objets de la liste.  
  
 Pour plus d'informations sur les classes de collection disponibles avec ATL, consultez [Classes de collection ATL](../../atl/atl-collection-classes.md).  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [CList Class](../../mfc/reference/clist-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)