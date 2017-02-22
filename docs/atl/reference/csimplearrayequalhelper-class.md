---
title: "CSimpleArrayEqualHelper Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSimpleArrayEqualHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleArrayEqualHelper class"
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CSimpleArrayEqualHelper Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est un programme d'assistance pour la classe de [CSimpleArray](../../atl/reference/csimplearray-class.md) .  
  
## Syntaxe  
  
```  
  
      template <  
   class T   
>  
class CSimpleArrayEqualHelper  
```  
  
#### Paramètres  
 `T`  
 Une classe dérivée.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleArrayEqualHelper::IsEqual](../Topic/CSimpleArrayEqualHelper::IsEqual.md)|\(Statique\) teste deux éléments objet d' `CSimpleArray` d'égalité.|  
  
## Notes  
 Cette classe Ctraits est un supplément à la classe d' `CSimpleArray` .  Elle fournit une méthode pour comparer deux éléments stockés dans un objet d' `CSimpleArray` .  Par défaut, les éléments sont comparés à l'aide de **operator\=\(\)**, mais si le tableau contient les types de données complexes qui ne disposent pas de leur propre opérateur d'égalité, vous devez substituer cette classe.  
  
## Configuration requise  
 **Header:** atlsimpcoll.h  
  
## Voir aussi  
 [CSimpleArray Class](../../atl/reference/csimplearray-class.md)   
 [CSimpleArrayEqualHelperFalse Class](../../atl/reference/csimplearrayequalhelperfalse-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)