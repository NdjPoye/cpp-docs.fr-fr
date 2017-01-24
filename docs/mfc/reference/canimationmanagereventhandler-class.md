---
title: "Classe CAnimationManagerEventHandler | Microsoft Docs"
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
  - "afxanimationcontroller/CAnimationManagerEventHandler"
  - "CAnimationManagerEventHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationManagerEventHandler (classe)"
ms.assetid: 6089ec07-e661-4805-b227-823b4652aade
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CAnimationManagerEventHandler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente un rappel, qui est appelé par l'API d'animation lorsque l'état d'un gestionnaire d'animation est modifié.  
  
## Syntaxe  
  
```  
class CAnimationManagerEventHandler : public CUIAnimationManagerEventHandlerBase<CAnimationManagerEventHandler>;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationManagerEventHandler::CAnimationManagerEventHandler](../Topic/CAnimationManagerEventHandler::CAnimationManagerEventHandler.md)|Construit un objet `CAnimationManagerEventHandler`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationManagerEventHandler::CreateInstance](../Topic/CAnimationManagerEventHandler::CreateInstance.md)|Crée une instance d'objet d' `CAnimationManagerEventHandler` .|  
|[CAnimationManagerEventHandler::OnManagerStatusChanged](../Topic/CAnimationManagerEventHandler::OnManagerStatusChanged.md)|Appelé lorsqu'un état du gestionnaire d'animations a changé.  \(Substitutions `CUIAnimationManagerEventHandlerBase::OnManagerStatusChanged`.\)|  
|[CAnimationManagerEventHandler::SetAnimationController](../Topic/CAnimationManagerEventHandler::SetAnimationController.md)|Stocke un pointeur vers le contrôleur de l'animation pour acheminer les événements.|  
  
## Notes  
 Ce gestionnaire d'événements est créé et transmis à la méthode IUIAnimationManager::SetManagerEventHandler, lorsque vous appelez CAnimationController::EnableAnimationManagerEvent.  
  
## Hiérarchie d'héritage  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationManagerEventHandlerBase`  
  
 `CAnimationManagerEventHandler`  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)