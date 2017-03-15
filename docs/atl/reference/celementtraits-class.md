---
title: "CElementTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CElementTraits<T>"
  - "ATL::CElementTraits"
  - "ATL.CElementTraits"
  - "ATL::CElementTraits<T>"
  - "CElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CElementTraits class"
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est utilisée par les classes de collection pour fournir des méthodes et des fonctions pour déplacer, copier, de comparaison, et opérations de hachage.  
  
## Syntaxe  
  
```  
  
      template<  
   typename T  
>  
class CElementTraits : public CDefaultElementTraits< T >  
```  
  
#### Paramètres  
 `T`  
 Le type de données à stocker dans la collection.  
  
## Notes  
 Cette classe fournit des fonctions static par défaut et des méthodes pour déplacer, copier, la comparaison, et les éléments de hachage stockés dans une classe de collection objet.  `CElementTraits` est spécifié comme fournisseur par défaut de ces opérations par les classes de collection [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md), et [CRBTree](../../atl/reference/crbtree-class.md).  
  
 Les implémentations par défaut suffiront pour les types de données simples, mais si les classes de collection sont utilisées pour stocker des objets plus complexes, des fonctions et des méthodes doivent être remplacées par des implémentations fournies par l'utilisateur.  
  
 Pour plus d'informations, consultez [Classes de collection ATL](../../atl/atl-collection-classes.md).  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [CDefaultElementTraits Class](../../atl/reference/cdefaultelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)