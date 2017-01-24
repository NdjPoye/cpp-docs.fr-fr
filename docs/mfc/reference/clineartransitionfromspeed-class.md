---
title: "Classe CLinearTransitionFromSpeed | Microsoft Docs"
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
  - "afxanimationcontroller/CLinearTransitionFromSpeed"
  - "CLinearTransitionFromSpeed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLinearTransitionFromSpeed (classe)"
ms.assetid: 8f159a1c-8893-4017-951e-09e5758aba7d
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CLinearTransitionFromSpeed
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule une transition de vitesse linéaire.  
  
## Syntaxe  
  
```  
class CLinearTransitionFromSpeed : public CBaseTransition;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CLinearTransitionFromSpeed::CLinearTransitionFromSpeed](../Topic/CLinearTransitionFromSpeed::CLinearTransitionFromSpeed.md)|Construit un objet de transition de vitesse linéaire et l'initialise avec une vitesse et une valeur finale.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CLinearTransitionFromSpeed::Create](../Topic/CLinearTransitionFromSpeed::Create.md)|Appelle la bibliothèque des transitions pour créer l'objet COM de la transition encapsulé.  \(Substitue [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CLinearTransitionFromSpeed::m\_dblFinalValue](../Topic/CLinearTransitionFromSpeed::m_dblFinalValue.md)|Valeur de la variable d'animation à la fin de la transition.|  
|[CLinearTransitionFromSpeed::m\_dblSpeed](../Topic/CLinearTransitionFromSpeed::m_dblSpeed.md)|Valeur absolue de la rapidité de la variable.|  
  
## Notes  
 Pendant une transition de vitesse linéaire, la valeur de la variable d'animation change  à un taux spécifié.  La durée de la transition est déterminée par la différence entre la valeur initiale et la valeur finale spécifiée.  Comme toutes les transitions sont effacées automatiquement, il est recommandé de les allouer à l'aide de l'opérateur new.  L'objet COM IUIAnimationTransition encapsulé est créé par CAnimationController::AnimateGroup ; jusque\-là sa valeur est NULL.  La modification des variables des membres après la création de cet objet COM n'a aucun effet.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CLinearTransitionFromSpeed](../../mfc/reference/clineartransitionfromspeed-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)