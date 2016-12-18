---
title: "CAutoPtr Class | Microsoft Docs"
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
  - "CAutoPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoPtr class"
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAutoPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente un objet de pointeur intelligent.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template<   
typename T  
>  
class CAutoPtr  
```  
  
#### Paramètres  
 `T`  
 Le type pointeur.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAutoPtr::CAutoPtr](../Topic/CAutoPtr::CAutoPtr.md)|Constructeur.|  
|[CAutoPtr::~CAutoPtr](../Topic/CAutoPtr::~CAutoPtr.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAutoPtr::Attach](../Topic/CAutoPtr::Attach.md)|Appelez cette méthode pour prendre la propriété d'un pointeur existant.|  
|[CAutoPtr::Detach](../Topic/CAutoPtr::Detach.md)|Appelez cette méthode pour libérer la propriété d'un pointeur.|  
|[CAutoPtr::Free](../Topic/CAutoPtr::Free.md)|Appelez cette méthode pour supprimer un objet vers lequel pointe `CAutoPtr`.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAutoPtr::operator T\*](../Topic/CAutoPtr::operator%20T*.md)|l'opérateur de cast.|  
|[CAutoPtr::operator \=](../Topic/CAutoPtr::operator%20=.md)|l'opérateur d'assignation.|  
|[CAutoPtr::operator \-\>](../Topic/CAutoPtr::operator%20-%3E.md)|L'opérateur de pointeur vers membre.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAutoPtr::m\_p](../Topic/CAutoPtr::m_p.md)|La variable de membre de pointeur.|  
  
## Notes  
 Cette classe fournit des méthodes pour créer et gérer un pointeur intelligent, qui permet de se protéger contre des fuites de mémoire en libérant automatiquement des ressources lorsqu'il se situe hors de portée.  
  
 De plus, le constructeur de copie d'`CAutoPtr` et l'opérateur d'assignation transfèrent la propriété du pointeur, copiant le pointeur de source au pointeur de destination et en plaçant le pointeur de source avec la valeur NULL.  Il est donc impossible d'avoir deux objets chacun d' `CAutoPtr` qui stocke le même pointeur, et cela réduit la possibilité de supprimer le même pointeur deux fois.  
  
 `CAutoPtr` simplifie également la création de collections de pointeurs.  Au lieu de dériver une classe de collection et de remplacer le destructeur, il est plus simple de créer une collection d'objets `CAutoPtr` .  Lorsque la collection est désactivée, les objets d' `CAutoPtr` aura pour résultat de la portée et se supprimeront automatiquement.  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md) et les variantes fonctionnent de la même façon qu' `CAutoPtr`, sauf qu'ils allouent et la mémoire disponible à l'aide de le tas différent s'exécute au lieu du C\+\+ **nouveau** et des opérateurs de **supprimer** .  [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) est semblable à `CAutoPtr`, la seule différence est qu'il utilise **vector new\[\]** et **vector delete\[\]** pour allouer et libérer de la mémoire.  
  
 Voir aussi [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) et le [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) lorsque des tableaux ou des listes de pointeurs intelligents sont requises.  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Exemple  
 [!code-cpp[NVC_ATL_Utilities#74](../../atl/codesnippet/CPP/cautoptr-class_1.cpp)]  
  
## Voir aussi  
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CAutoVectorPtr Class](../../atl/reference/cautovectorptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)