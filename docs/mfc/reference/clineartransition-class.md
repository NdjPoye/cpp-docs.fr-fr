---
title: "Classe CLinearTransition | Microsoft Docs"
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
  - "CLinearTransition"
  - "afxanimationcontroller/CLinearTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLinearTransition (classe)"
ms.assetid: 7fcb2dba-beb8-4933-9f5d-3b7fb1585ef0
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CLinearTransition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule une transition linéaire.  
  
## Syntaxe  
  
```  
class CLinearTransition : public CBaseTransition;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CLinearTransition::CLinearTransition](../Topic/CLinearTransition::CLinearTransition.md)|Construit un objet de transition linéaire et l'initialise avec une durée et une valeur finale.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CLinearTransition::Create](../Topic/CLinearTransition::Create.md)|Appelle la bibliothèque des transitions pour créer l'objet COM de la transition encapsulé.  \(Substitue [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CLinearTransition::m\_dblFinalValue](../Topic/CLinearTransition::m_dblFinalValue.md)|Valeur de la variable d'animation à la fin de la transition.|  
|[CLinearTransition::m\_duration](../Topic/CLinearTransition::m_duration.md)|Durée de la transition.|  
  
## Notes  
 Pendant une transition linéaire, la valeur des transitions de la variable d'animation passe de manière linéaire de sa valeur initiale à une valeur définitive spécifiée.  Comme toutes les transitions sont effacées automatiquement, il est recommandé de les allouer à l'aide de l'opérateur new.  L'objet COM IUIAnimationTransition encapsulé est créé par CAnimationController::AnimateGroup ; jusque\-là sa valeur est NULL.  La modification des variables des membres après la création de cet objet COM n'a aucun effet.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CLinearTransition](../../mfc/reference/clineartransition-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)