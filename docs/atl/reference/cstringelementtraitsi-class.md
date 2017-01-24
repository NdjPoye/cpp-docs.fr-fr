---
title: "CStringElementTraitsI Class | Microsoft Docs"
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
  - "ATL::CStringElementTraitsI"
  - "CStringElementTraitsI"
  - "ATL.CStringElementTraitsI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringElementTraitsI class"
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringElementTraitsI Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des fonctions static liées aux chaînes stockées dans des objets de classe de collection.  Il est semblable à [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md), mais effectue des comparaisons ne respectant pas la casse.  
  
## Syntaxe  
  
```  
  
      template<  
   typename T,  
   class CharTraits = CDefaultCharTraits< T::XCHAR >  
>  
class CStringElementTraitsI : public CElementTraitsBase< T >  
```  
  
#### Paramètres  
 `T`  
 Le type de données à stocker dans la collection.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CStringElementTraitsI::INARGTYPE](../Topic/CStringElementTraitsI::INARGTYPE.md)|Le type de données à utiliser pour ajouter des éléments à l'objet de classe de collection.|  
|[CStringElementTraitsI::OUTARGTYPE](../Topic/CStringElementTraitsI::OUTARGTYPE.md)|Le type de données à utiliser pour récupérer des éléments de l'objet de classe de collection.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CStringElementTraitsI::CompareElements](../Topic/CStringElementTraitsI::CompareElements.md)|Appelez cette fonction statique pour comparer deux éléments de chaîne pour l'égalité, en ignorant les différences de casse.|  
|[CStringElementTraitsI::CompareElementsOrdered](../Topic/CStringElementTraitsI::CompareElementsOrdered.md)|Appelez cette fonction statique pour comparer deux éléments de chaîne, en ignorant les différences de casse.|  
|[CStringElementTraitsI::Hash](../Topic/CStringElementTraitsI::Hash.md)|Appelez cette fonction statique pour calculer une valeur de hachage pour l'élément donné de chaîne.|  
  
## Notes  
 Cette classe fournit des fonctions statiques pour comparer des chaînes et pour créer une valeur de hachage.  Ces fonctions sont utiles lorsque vous utilisez une classe de collection pour stocker des données basées sur une chaîne.  Utilisez [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) lorsque les objets String sont soit avec traité comme références.  
  
 Pour plus d'informations, consultez [Classes de collection ATL](../../atl/atl-collection-classes.md).  
  
## Hiérarchie d'héritage  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringElementTraitsI`  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [CElementTraitsBase Class](../../atl/reference/celementtraitsbase-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CStringElementTraits Class](../../atl/reference/cstringelementtraits-class.md)