---
title: "Classe CBaseTransition | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CBaseTransition"
  - "afxanimationcontroller/CBaseTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBaseTransition (classe)"
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Classe CBaseTransition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une transition de base.  
  
## Syntaxe  
  
```  
class CBaseTransition : public CObject;  
```  
  
## Membres  
  
### Énumérations publique  
  
|Nom|Description|  
|---------|-----------------|  
|[Énumération CBaseTransition::TRANSITION\_TYPE](../Topic/CBaseTransition::TRANSITION_TYPE%20Enumeration.md)|Définit les types de transition prises en charge actuellement par l'implémentation MFC de l'API Animation Windows.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CBaseTransition::CBaseTransition](../Topic/CBaseTransition::CBaseTransition.md)|Construit un objet de transtion de base.|  
|[CBaseTransition::~CBaseTransition](../Topic/CBaseTransition::~CBaseTransition.md)|Le destructeur.  Appelé lorsqu'un objet de la transition est détruit.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CBaseTransition::AddToStoryboard](../Topic/CBaseTransition::AddToStoryboard.md)|Ajoute une transition à un storyboard.|  
|[CBaseTransition::AddToStoryboardAtKeyframes](../Topic/CBaseTransition::AddToStoryboardAtKeyframes.md)|Ajoute une transition à un storyboard.|  
|[CBaseTransition::Clear](../Topic/CBaseTransition::Clear.md)|Libère l'objet COM IUIAnimationTransition encapsulé.|  
|[CBaseTransition::Create](../Topic/CBaseTransition::Create.md)|Crée une transition COM.|  
|[CBaseTransition::GetEndKeyframe](../Topic/CBaseTransition::GetEndKeyframe.md)|Renvoie la première image clé.|  
|[CBaseTransition::GetRelatedVariable](../Topic/CBaseTransition::GetRelatedVariable.md)|Retourne un pointeur à la variable connexe.|  
|[CBaseTransition::GetStartKeyframe](../Topic/CBaseTransition::GetStartKeyframe.md)|Renvoie la première image clé.|  
|[CBaseTransition::GetTransition](../Topic/CBaseTransition::GetTransition.md)|Surchargé.  Retourne un pointeur à l'objet de transition COM sous\-jacent.|  
|[CBaseTransition::GetType](../Topic/CBaseTransition::GetType.md)|Retourne le type de transition.|  
|[CBaseTransition::IsAdded](../Topic/CBaseTransition::IsAdded.md)|Indique si une transition a été ajoutée à un storyboard.|  
|[CBaseTransition::SetKeyframes](../Topic/CBaseTransition::SetKeyframes.md)|Définit les images clés d'une transition.|  
|[CBaseTransition::SetRelatedVariable](../Topic/CBaseTransition::SetRelatedVariable.md)|Établit une relation entre la variable d'animation et la transition.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CBaseTransition::m\_bAdded](../Topic/CBaseTransition::m_bAdded.md)|indique si une transition a été ajoutée à un storyboard.|  
|[CBaseTransition::m\_pEndKeyframe](../Topic/CBaseTransition::m_pEndKeyframe.md)|Stocke un pointeur à l'image clé qui spécifie la fin de la transition.|  
|[CBaseTransition::m\_pRelatedVariable](../Topic/CBaseTransition::m_pRelatedVariable.md)|Pointeur vers une variable d'animation qui est animée avec la transition stockée dans m\_transition.|  
|[CBaseTransition::m\_pStartKeyframe](../Topic/CBaseTransition::m_pStartKeyframe.md)|Stocke un pointeur à l'image clé qui spécifie le début de la transition.|  
|[CBaseTransition::m\_transition](../Topic/CBaseTransition::m_transition.md)|Stocke un pointeur à IUIAnimationTransition.  NULL si un objet de transition COM n'a pas été créé.|  
|[CBaseTransition::m\_type](../Topic/CBaseTransition::m_type.md)|Stocke le type de transition.|  
  
## Notes  
 Cette classe encapsule l'interface IUIAnimationTransition et sert de classe de base pour toutes les transitions.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)