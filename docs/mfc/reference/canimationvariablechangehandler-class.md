---
title: "Classe CAnimationVariableChangeHandler | Microsoft Docs"
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
  - "afxanimationcontroller/CAnimationVariableChangeHandler"
  - "CAnimationVariableChangeHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationVariableChangeHandler (classe)"
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CAnimationVariableChangeHandler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente un rappel, qui est appelé par l'API d'animation lorsque la valeur d'une variable de l'animation est modifiée.  
  
## Syntaxe  
  
```  
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|Construit un objet `CAnimationVariableChangeHandler`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|`CAnimationVariableChangeHandler::CreateInstance`|Crée une instance d'objet d' `CAnimationVariableChangeHandler` .|  
|[CAnimationVariableChangeHandler::OnValueChanged](../Topic/CAnimationVariableChangeHandler::OnValueChanged.md)|Appelé lorsqu'une valeur d'une variable d'animation change.  \(Substitutions `CUIAnimationVariableChangeHandlerBase::OnValueChanged`.\)|  
|[CAnimationVariableChangeHandler::SetAnimationController](../Topic/CAnimationVariableChangeHandler::SetAnimationController.md)|Stocke un pointeur vers le contrôleur de l'animation pour acheminer les événements.|  
  
## Notes  
 Ce gestionnaire d'événements est créé et passé à la méthode d' `IUIAnimationVariable::SetVariableChangeHandler` , lorsque vous appelez `CAnimationVariable::EnableValueChangedEvent` ou `CAnimationBaseObject::EnableValueChangedEvent` \(qui active cet événement pour toutes les variables d'animation encapsulées dans un objet d'animation\).  
  
## Hiérarchie d'héritage  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableChangeHandlerBase`  
  
 `CAnimationVariableChangeHandler`  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)