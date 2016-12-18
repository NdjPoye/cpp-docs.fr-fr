---
title: "CDefaultCompareTraits Class | Microsoft Docs"
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
  - "ATL.CDefaultCompareTraits<T>"
  - "ATL::CDefaultCompareTraits"
  - "ATL.CDefaultCompareTraits"
  - "ATL::CDefaultCompareTraits<T>"
  - "CDefaultCompareTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDefaultCompareTraits class"
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDefaultCompareTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des fonctions de comparaison par défaut d'élément.  
  
## Syntaxe  
  
```  
  
      template<  
   typename T  
>  
class CDefaultCompareTraits  
```  
  
#### Paramètres  
 `T`  
 Le type de données à stocker dans la collection.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDefaultCompareTraits::CompareElements](../Topic/CDefaultCompareTraits::CompareElements.md)|\(Statique\) appelle cette fonction pour comparer deux éléments d'égalité.|  
|[CDefaultCompareTraits::CompareElementsOrdered](../Topic/CDefaultCompareTraits::CompareElementsOrdered.md)|\(Statique\) appelle cette fonction pour déterminer le supérieur et peu d'élément.|  
  
## Notes  
 Cette classe contient deux fonctions statiques pour comparer des éléments stockés dans un objet de classe de collection.  Cette classe est utilisée par [classe de CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Pour plus d'informations, consultez [Classes de collection ATL](../../atl/atl-collection-classes.md).  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)