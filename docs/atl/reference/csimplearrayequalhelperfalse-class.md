---
title: "CSimpleArrayEqualHelperFalse Class | Microsoft Docs"
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
  - "ATL.CSimpleArrayEqualHelperFalse<T>"
  - "ATL::CSimpleArrayEqualHelperFalse"
  - "ATL.CSimpleArrayEqualHelperFalse"
  - "ATL::CSimpleArrayEqualHelperFalse<T>"
  - "CSimpleArrayEqualHelperFalse"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleArrayEqualHelperFalse class"
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleArrayEqualHelperFalse Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est un programme d'assistance pour la classe de [CSimpleArray](../../atl/reference/csimplearray-class.md) .  
  
## Syntaxe  
  
```  
  
      template <  
   class T   
>   
class CSimpleArrayEqualHelperFalse  
```  
  
#### Paramètres  
 `T`  
 Une classe dérivée.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleArrayEqualHelperFalse::IsEqual](../Topic/CSimpleArrayEqualHelperFalse::IsEqual.md)|Retourne \(statique\) false.|  
  
## Notes  
 Cette classe Ctraits est un complément à la classe d' `CSimpleArray` .  Elle retourne toujours la valeur false, et en outre, appelle `ATLASSERT` avec un argument de faux s'il est jamais référencée.  Dans les situations où le test d'égalité n'est pas suffisamment défini, cette classe fournit un tableau contenant les éléments pour fonctionner correctement pour la plupart des méthodes mais échec d'une manière bien définie pour les méthodes qui dépendent des comparaisons telles que [CSimpleArray::Find](../Topic/CSimpleArray::Find.md).  
  
## Configuration requise  
 **Header:** atlsimpcoll.h  
  
## Voir aussi  
 [CSimpleArrayEqualHelper Class](../../atl/reference/csimplearrayequalhelper-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)