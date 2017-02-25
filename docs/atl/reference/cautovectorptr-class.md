---
title: "CAutoVectorPtr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAutoVectorPtr"
  - "ATL.CAutoVectorPtr"
  - "ATL.CAutoVectorPtr<T>"
  - "CAutoVectorPtr"
  - "ATL::CAutoVectorPtr<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoVectorPtr class"
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CAutoVectorPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente un objet de pointeur intelligent à nouveau vectorielles et des opérateurs delete.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template<  
typename T  
> class CAutoVectorPtr  
```  
  
#### Paramètres  
 `T`  
 Le type pointeur.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAutoVectorPtr::CAutoVectorPtr](../Topic/CAutoVectorPtr::CAutoVectorPtr.md)|Constructeur.|  
|[CAutoVectorPtr::~CAutoVectorPtr](../Topic/CAutoVectorPtr::~CAutoVectorPtr.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAutoVectorPtr::Allocate](../Topic/CAutoVectorPtr::Allocate.md)|Appelez cette méthode pour allouer de la mémoire requise par le tableau d'objets pointés pointe vers `CAutoVectorPtr`.|  
|[CAutoVectorPtr::Attach](../Topic/CAutoVectorPtr::Attach.md)|Appelez cette méthode pour prendre la propriété d'un pointeur existant.|  
|[CAutoVectorPtr::Detach](../Topic/CAutoVectorPtr::Detach.md)|Appelez cette méthode pour libérer la propriété d'un pointeur.|  
|[CAutoVectorPtr::Free](../Topic/CAutoVectorPtr::Free.md)|Appelez cette méthode pour supprimer un objet vers lequel pointe `CAutoVectorPtr`.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAutoVectorPtr::operator T \*](../Topic/CAutoVectorPtr::operator%20T%20*.md)|l'opérateur de cast.|  
|[CAutoVectorPtr::operator \=](../Topic/CAutoVectorPtr::operator%20=.md)|l'opérateur d'assignation.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAutoVectorPtr::m\_p](../Topic/CAutoVectorPtr::m_p.md)|La variable de membre de pointeur.|  
  
## Notes  
 Cette classe fournit des méthodes pour créer et gérer un pointeur intelligent, qui permet de se protéger contre des fuites de mémoire en libérant automatiquement des ressources lorsqu'il se situe hors de portée.  `CAutoVectorPtr` est semblable à `CAutoPtr`, la seule différence étant que utilise [nouveaux vectoriels &#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md) et [suppression vectorielle &#91;&#93;](../Topic/operator%20delete\(%3Cnew%3E\).md) d' `CAutoVectorPtr` d'allouer et libérer de la mémoire au lieu du C\+\+ **nouveau** et des opérateurs de **supprimer** .  Consultez [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) si les classes de collection d' `CAutoVectorPtr` sont requises.  
  
 Consultez [CAutoPtr](../../atl/reference/cautoptr-class.md) pour obtenir un exemple d'utiliser une classe intelligente du pointeur.  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [CAutoPtr Class](../../atl/reference/cautoptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)