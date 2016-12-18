---
title: "Classe CConstantTransition | Microsoft Docs"
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
  - "afxanimationcontroller/CConstantTransition"
  - "CConstantTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CConstantTransition (classe)"
ms.assetid: f6fa4780-a71b-4cd6-80aa-d4792ace36c2
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CConstantTransition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule une transition constante.  
  
## Syntaxe  
  
```  
class CConstantTransition : public CBaseTransition;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CConstantTransition::CConstantTransition](../Topic/CConstantTransition::CConstantTransition.md)|Construit un objet de transition et initialise sa durée.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CConstantTransition::Create](../Topic/CConstantTransition::Create.md)|Appelle la bibliothèque des transitions pour créer l'objet COM de la transition encapsulé.  \(Substitue [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CConstantTransition::m\_duration](../Topic/CConstantTransition::m_duration.md)|Durée de la transition.|  
  
## Notes  
 Pendant une transition constante, la valeur d'une variable d'animation conserve la valeur initiale pendant la durée de la transition.  Comme toutes les transitions sont effacées automatiquement, il est recommandé de les allouer à l'aide de l'opérateur new.  L'objet COM IUIAnimationTransition encapsulé est créé par CAnimationController::AnimateGroup ; jusque\-là sa valeur est NULL.  La modification des variables des membres après la création de cet objet COM n'a aucun effet.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CConstantTransition](../../mfc/reference/cconstanttransition-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)