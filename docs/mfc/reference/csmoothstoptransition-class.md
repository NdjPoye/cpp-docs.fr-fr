---
title: "Classe CSmoothStopTransition | Microsoft Docs"
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
  - "CSmoothStopTransition"
  - "afxanimationcontroller/CSmoothStopTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSmoothStopTransition (classe)"
ms.assetid: e1a4b476-6f96-43dd-90db-870a64406b85
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CSmoothStopTransition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule une transition d'arrêt en douceur.  
  
## Syntaxe  
  
```  
class CSmoothStopTransition : public CBaseTransition;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSmoothStopTransition::CSmoothStopTransition](../Topic/CSmoothStopTransition::CSmoothStopTransition.md)|Construit une transition d'arrêt lissé et initialise sa durée maximale et sa valeur finale.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSmoothStopTransition::Create](../Topic/CSmoothStopTransition::Create.md)|Appelle la bibliothèque des transitions pour créer l'objet COM de la transition encapsulé.  \(Substitue [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSmoothStopTransition::m\_dblFinalValue](../Topic/CSmoothStopTransition::m_dblFinalValue.md)|Valeur de la variable d'animation à la fin de la transition.|  
|[CSmoothStopTransition::m\_maximumDuration](../Topic/CSmoothStopTransition::m_maximumDuration.md)|Durée maximale de la transition.|  
  
## Notes  
 Une transition d'arrêt lissé ralentit à mesure qu'il approche d'une valeur finale donnée, et l'atteint avec une rapidité de zéro.  La durée de la transition est déterminée par la rapidité initiale, la différence entre les valeurs initiales et finales, et la durée maximale spécifiée.  Si aucune solution ne représente un arc parabolique unique, cette méthode crée une transition cubique.  Comme toutes les transitions sont effacées automatiquement, il est recommandé de les allouer à l'aide de l'opérateur new.  L'objet COM IUIAnimationTransition encapsulé est créé par CAnimationController::AnimateGroup ; jusque\-là sa valeur est NULL.  La modification des variables des membres après la création de cet objet COM n'a aucun effet.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSmoothStopTransition](../../mfc/reference/csmoothstoptransition-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)