---
title: "CStringElementTraits Class | Microsoft Docs"
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
  - "ATL.CStringElementTraits<T>"
  - "ATL::CStringElementTraits<T>"
  - "CStringElementTraits"
  - "ATL.CStringElementTraits"
  - "ATL::CStringElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringElementTraits class"
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des fonctions static utilisées par les classes de collection enregistrant des objets d' `CString` .  
  
## Syntaxe  
  
```  
  
      template<  
   typename T   
>  
class CStringElementTraits  
```  
  
#### Paramètres  
 `T`  
 Le type de données à stocker dans la collection.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CStringElementTraits::INARGTYPE](../Topic/CStringElementTraits::INARGTYPE.md)|Le type de données à utiliser pour ajouter des éléments à l'objet de classe de collection.|  
|[CStringElementTraits::OUTARGTYPE](../Topic/CStringElementTraits::OUTARGTYPE.md)|Le type de données à utiliser pour récupérer des éléments de l'objet de classe de collection.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CStringElementTraits::CompareElements](../Topic/CStringElementTraits::CompareElements.md)|\(Statique\) appelle cette fonction pour comparer deux éléments de chaîne pour l'égalité.|  
|[CStringElementTraits::CompareElementsOrdered](../Topic/CStringElementTraits::CompareElementsOrdered.md)|\(Statique\) appelle cette fonction pour comparer deux éléments de chaîne.|  
|[CStringElementTraits::CopyElements](../Topic/CStringElementTraits::CopyElements.md)|\(Statique\) appelle cette fonction pour copier des éléments d' `CString` stockés dans un objet de classe de collection.|  
|[CStringElementTraits::Hash](../Topic/CStringElementTraits::Hash.md)|\(Statique\) appelle cette fonction pour calculer une valeur de hachage pour l'élément donné de chaîne.|  
|[CStringElementTraits::RelocateElements](../Topic/CStringElementTraits::RelocateElements.md)|\(Statique\) appelle cette fonction pour déplacer des éléments d' `CString` stockés dans un objet de classe de collection.|  
  
## Notes  
 Cette classe fournit des fonctions statiques pour copier, déplacer, puis comparer des chaînes et pour créer une valeur de hachage.  Ces fonctions sont utiles lorsque vous utilisez une classe de collection pour stocker des données basées sur une chaîne.  Utilisation [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) lorsque des comparaisons ne respectant pas la casse sont requis.  Utilisez [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) lorsque les objets String doivent être traités comme références.  
  
 Pour plus d'informations, consultez [Classes de collection ATL](../../atl/atl-collection-classes.md).  
  
## Configuration requise  
 **Header:** cstringt.h  
  
## Voir aussi  
 [CElementTraitsBase Class](../../atl/reference/celementtraitsbase-class.md)   
 [CStringElementTraitsI Class](../../atl/reference/cstringelementtraitsi-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)