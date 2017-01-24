---
title: "CSimpleMapEqualHelper Class | Microsoft Docs"
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
  - "CSimpleMapEqualHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleMapEqualHelper class"
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleMapEqualHelper Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est un programme d'assistance pour la classe de [CSimpleMap](../../atl/reference/csimplemap-class.md) .  
  
## Syntaxe  
  
```  
  
      template <  
   class TKey,  
   class TVal   
>  
class CSimpleMapEqualHelper  
```  
  
#### Paramètres  
 `TKey`  
 l'élément clé.  
  
 `TVal`  
 l'élément de valeur.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleMapEqualHelper::IsEqualKey](../Topic/CSimpleMapEqualHelper::IsEqualKey.md)|\(Statique\) teste deux clés d'égalité.|  
|[CSimpleMapEqualHelper::IsEqualValue](../Topic/CSimpleMapEqualHelper::IsEqualValue.md)|\(Statique\) teste deux valeurs pour déterminer l'égalité.|  
  
## Notes  
 Cette classe Ctraits est un supplément à la classe d' `CSimpleMap` .  Elle fournit des méthodes pour comparer deux éléments objet d' `CSimpleMap` \(en particulier, la clé et les composants de valeur\) pour l'égalité.  Par défaut, les clés et les valeurs sont comparées à l'aide de `operator==()`, mais si le mappage contient les types de données complexes qui ne disposent pas de leur propre opérateur d'égalité, cette classe peut être substituée pour fournir la fonctionnalité requise supplémentaire.  
  
## Configuration requise  
 **en\-tête :** atlsimpcoll.h  
  
## Voir aussi  
 [CSimpleMapEqualHelperFalse Class](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)