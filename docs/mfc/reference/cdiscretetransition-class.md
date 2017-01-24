---
title: "Classe CDiscreteTransition | Microsoft Docs"
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
  - "CDiscreteTransition"
  - "afxanimationcontroller/CDiscreteTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDiscreteTransition (classe)"
ms.assetid: b4d84fb3-ccaa-451c-a69b-6b50dcb9b9c8
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CDiscreteTransition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule une transition discrète.  
  
## Syntaxe  
  
```  
class CDiscreteTransition : public CBaseTransition;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDiscreteTransition::CDiscreteTransition](../Topic/CDiscreteTransition::CDiscreteTransition.md)|Construit un objet de transition discret et initialise ses paramètres.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDiscreteTransition::Create](../Topic/CDiscreteTransition::Create.md)|Appelle la bibliothèque des transitions pour créer l'objet COM de la transition encapsulé.  \(Substitue [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDiscreteTransition::m\_dblFinalValue](../Topic/CDiscreteTransition::m_dblFinalValue.md)|Valeur de la variable d'animation à la fin de la transition.|  
|[CDiscreteTransition::m\_delay](../Topic/CDiscreteTransition::m_delay.md)|Durée à l'issue de laquelle le commutateur instantané passe à la valeur finale.|  
|[CDiscreteTransition::m\_hold](../Topic/CDiscreteTransition::m_hold.md)|Durée de maintien de la variable comme valeur finale.|  
  
## Notes  
 Pendant une transition discrète, la variable d'animation conserve la valeur initiale pendant un délai spécifié, puis passe instantanément à une valeur définitive spécifiée et conserve cette valeur pendant une durée donnée.  Comme toutes les transitions sont effacées automatiquement, il est recommandé de les allouer à l'aide de l'opérateur new.  L'objet COM IUIAnimationTransition encapsulé est créé par CAnimationController::AnimateGroup ; jusque\-là sa valeur est NULL.  La modification des variables des membres après la création de cet objet COM n'a aucun effet.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CDiscreteTransition](../../mfc/reference/cdiscretetransition-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)