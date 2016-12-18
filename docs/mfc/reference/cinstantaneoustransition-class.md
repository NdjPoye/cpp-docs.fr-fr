---
title: "Classe CInstantaneousTransition | Microsoft Docs"
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
  - "afxanimationcontroller/CInstantaneousTransition"
  - "CInstantaneousTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInstantaneousTransition (classe)"
ms.assetid: c3d5121f-2c6b-4221-9e57-10e082a31120
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CInstantaneousTransition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule une transition instantanée.  
  
## Syntaxe  
  
```  
class CInstantaneousTransition : public CBaseTransition;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CInstantaneousTransition::CInstantaneousTransition](../Topic/CInstantaneousTransition::CInstantaneousTransition.md)|Construit un objet de transition et initialise sa valeur finale.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CInstantaneousTransition::Create](../Topic/CInstantaneousTransition::Create.md)|Appelle la bibliothèque des transitions pour créer l'objet COM de la transition encapsulé.  \(Substitue [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CInstantaneousTransition::m\_dblFinalValue](../Topic/CInstantaneousTransition::m_dblFinalValue.md)|Valeur de la variable d'animation à la fin de la transition.|  
  
## Notes  
 Pendant une transition instantanée, la valeur de la variable d'animation change instantanément en passant de sa valeur actuelle à une valeur finale spécifiée.  La durée de cette transition est toujours égale à zéro.  Comme toutes les transitions sont effacées automatiquement, il est recommandé de les allouer à l'aide de l'opérateur new.  L'objet COM IUIAnimationTransition encapsulé est créé par CAnimationController::AnimateGroup ; jusque\-là sa valeur est NULL.  La modification des variables des membres après la création de cet objet COM n'a aucun effet.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CInstantaneousTransition](../../mfc/reference/cinstantaneoustransition-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)