---
title: "Classe CSinusoidalTransitionFromVelocity | Microsoft Docs"
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
  - "CSinusoidalTransitionFromVelocity"
  - "afxanimationcontroller/CSinusoidalTransitionFromVelocity"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSinusoidalTransitionFromVelocity (classe)"
ms.assetid: cc885f17-b84b-45ee-8f1f-36a8bbb7adad
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CSinusoidalTransitionFromVelocity
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule une transition de vitesse sinusoïdale dont l'amplitude est déterminée par la rapidité initiale de la variable de l'animation.  
  
## Syntaxe  
  
```  
class CSinusoidalTransitionFromVelocity : public CBaseTransition;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity](../Topic/CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity.md)|Construit un objet de transition.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSinusoidalTransitionFromVelocity::Create](../Topic/CSinusoidalTransitionFromVelocity::Create.md)|Appelle la bibliothèque des transitions pour créer l'objet COM de la transition encapsulé.  \(Substitue [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSinusoidalTransitionFromVelocity::m\_duration](../Topic/CSinusoidalTransitionFromVelocity::m_duration.md)|Durée de la transition.|  
|[CSinusoidalTransitionFromVelocity::m\_period](../Topic/CSinusoidalTransitionFromVelocity::m_period.md)|Période d'oscillation de l'onde sinusoïdale en secondes.|  
  
## Notes  
 La valeur de la variable d'animation oscille autour de la valeur initiale sur la durée entière d'une transition de plage sinusoïdale.  L'amplitude de l'oscillation est déterminée par la rapidité de la variable d'animation lorsque la transition commence.  Comme toutes les transitions sont effacées automatiquement, il est recommandé de les allouer à l'aide de l'opérateur new.  L'objet COM IUIAnimationTransition encapsulé est créé par CAnimationController::AnimateGroup ; jusque\-là sa valeur est NULL.  La modification des variables des membres après la création de cet objet COM n'a aucun effet.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromVelocity](../../mfc/reference/csinusoidaltransitionfromvelocity-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)