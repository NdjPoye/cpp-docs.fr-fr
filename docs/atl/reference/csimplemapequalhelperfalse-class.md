---
title: "CSimpleMapEqualHelperFalse Class | Microsoft Docs"
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
  - "ATL::CSimpleMapEqualHelperFalse"
  - "CSimpleMapEqualHelperFalse"
  - "ATL.CSimpleMapEqualHelperFalse"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleMapEqualHelperFalse class"
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleMapEqualHelperFalse Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est un programme d'assistance pour la classe de [CSimpleMap](../../atl/reference/csimplemap-class.md) .  
  
## Syntaxe  
  
```  
  
template < class TKey, class TVal > class CSimpleMapEqualHelperFalse  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleMapEqualHelperFalse::IsEqualKey](../Topic/CSimpleMapEqualHelperFalse::IsEqualKey.md)|\(Statique\) teste deux clés d'égalité.|  
|[CSimpleMapEqualHelperFalse::IsEqualValue](../Topic/CSimpleMapEqualHelperFalse::IsEqualValue.md)|Retourne \(statique\) false.|  
  
## Notes  
 Cette classe Ctraits est un supplément à la classe d' `CSimpleMap` .  Elle fournit une méthode pour comparer deux éléments contenus dans l'objet d' `CSimpleMap` , spécifiquement deux éléments de valeur ou deux éléments clé.  
  
 La comparaison de valeurs retourne toujours la valeur false, et en outre, appelle `ATLASSERT` avec un argument de faux s'il est jamais référencée.  Dans les situations où le test d'égalité n'est pas suffisamment défini, cette classe fournit un mappage qui contient des paires clé\/valeur pour fonctionner correctement pour la plupart des méthodes mais échec d'une manière bien définie pour les méthodes qui dépendent des comparaisons telles que [CSimpleMap::FindVal](../Topic/CSimpleMap::FindVal.md).  
  
## Configuration requise  
 **Header:** atlsimpcoll.h  
  
## Voir aussi  
 [CSimpleMapEqualHelper Class](../../atl/reference/csimplemapequalhelper-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)