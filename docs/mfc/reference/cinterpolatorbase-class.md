---
title: "Classe CInterpolatorBase | Microsoft Docs"
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
  - "afxanimationcontroller/CInterpolatorBase"
  - "CInterpolatorBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInterpolatorBase (classe)"
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CInterpolatorBase
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente un rappel, qui est appelé par l'API d'animation lorsqu'elle doit calculer la nouvelle valeur d'une variable de l'animation.  
  
## Syntaxe  
  
```  
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CInterpolatorBase::CInterpolatorBase](../Topic/CInterpolatorBase::CInterpolatorBase.md)|Construit l'objet d' `CInterpolatorBase` .|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CInterpolatorBase::CreateInstance](../Topic/CInterpolatorBase::CreateInstance.md)|Crée une instance d' `CInterpolatorBase` et stocke un pointeur vers une interclasseuse personnalisée, qui gérera les événements.|  
|[CInterpolatorBase::GetDependencies](../Topic/CInterpolatorBase::GetDependencies.md)|Obtient les dépendances de l'interpolateur.  \(Substitutions `CUIAnimationInterpolatorBase::GetDependencies`.\)|  
|[CInterpolatorBase::GetDuration](../Topic/CInterpolatorBase::GetDuration.md)|Obtient la durée de l'interpolateur.  \(Substitutions `CUIAnimationInterpolatorBase::GetDuration`.\)|  
|[CInterpolatorBase::GetFinalValue](../Topic/CInterpolatorBase::GetFinalValue.md)|Obtient la valeur finale obtenue par l'interpolateur.  \(Substitutions `CUIAnimationInterpolatorBase::GetFinalValue`.\)|  
|[CInterpolatorBase::InterpolateValue](../Topic/CInterpolatorBase::InterpolateValue.md)|Interpole la valeur à un offset donné \(substitutions `CUIAnimationInterpolatorBase::InterpolateValue`.\)|  
|[CInterpolatorBase::InterpolateVelocity](../Topic/CInterpolatorBase::InterpolateVelocity.md)|Interpole la vitesse à un offset donné \(substitutions `CUIAnimationInterpolatorBase::InterpolateVelocity`.\)|  
|[CInterpolatorBase::SetCustomInterpolator](../Topic/CInterpolatorBase::SetCustomInterpolator.md)|Stocke un pointeur à l'interpolateur personnalisé qui doit gérer les événements.|  
|[CInterpolatorBase::SetDuration](../Topic/CInterpolatorBase::SetDuration.md)|Définit la durée de l'interclasseuse \(substitutions `CUIAnimationInterpolatorBase::SetDuration`.\)|  
|[CInterpolatorBase::SetInitialValueAndVelocity](../Topic/CInterpolatorBase::SetInitialValueAndVelocity.md)|Définit la valeur initiale de l'interpolateur et la rapidité.  \(Substitutions `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`.\)|  
  
## Notes  
 Ce gestionnaire est créé et passé à `IUIAnimationTransitionFactory::CreateTransition` lorsqu'un objet d' `CCustomTransition` est créé comme une partie du processus d'initialisation d'animation \(lancé par `CAnimationController::AnimateGroup`\).  Habituellement vous n'avez pas besoin d'utiliser cette classe directement, il conduit à tous les événements à `CCustomInterpolator`\- la classe dérivée, dont le pointeur est passé au constructeur d' `CCustomTransition`.  
  
## Hiérarchie d'héritage  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationInterpolatorBase`  
  
 `CInterpolatorBase`  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)