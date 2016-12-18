---
title: "Classe CAnimationVariable | Microsoft Docs"
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
  - "CAnimationVariable"
  - "afxanimationcontroller/CAnimationVariable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationVariable (classe)"
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CAnimationVariable
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une variable de l'animation.  
  
## Syntaxe  
  
```  
class CAnimationVariable;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationVariable::CAnimationVariable](../Topic/CAnimationVariable::CAnimationVariable.md)|Construit un objet d'animation variable.|  
|[CAnimationVariable::~CAnimationVariable](../Topic/CAnimationVariable::~CAnimationVariable.md)|Le destructeur.  Appelé lorsqu'un objet CAnimationVariable est détruit.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationVariable::AddTransition](../Topic/CAnimationVariable::AddTransition.md)|Ajoute une transition.|  
|[CAnimationVariable::ApplyTransitions](../Topic/CAnimationVariable::ApplyTransitions.md)|Ajoute des transitions de la liste interne au storyboard.|  
|[CAnimationVariable::ClearTransitions](../Topic/CAnimationVariable::ClearTransitions.md)|Efface les transitions.|  
|[CAnimationVariable::Create](../Topic/CAnimationVariable::Create.md)|Crée l'objet COM de la variable d'animation sous\-jacente.|  
|[CAnimationVariable::CreateTransitions](../Topic/CAnimationVariable::CreateTransitions.md)|Crée toutes les transitions à appliquer à cette variable d'animation.|  
|[CAnimationVariable::EnableIntegerValueChangedEvent](../Topic/CAnimationVariable::EnableIntegerValueChangedEvent.md)|Active ou désactive l'événement IntegerValueChanged.|  
|[CAnimationVariable::EnableValueChangedEvent](../Topic/CAnimationVariable::EnableValueChangedEvent.md)|Active ou désactive l'événement ValueChanged.|  
|[CAnimationVariable::GetDefaultValue](../Topic/CAnimationVariable::GetDefaultValue.md)|Retourne la valeur par défaut.|  
|[CAnimationVariable::GetParentAnimationObject](../Topic/CAnimationVariable::GetParentAnimationObject.md)|Retourne l'objet d'animation parent.|  
|[CAnimationVariable::GetValue](../Topic/CAnimationVariable::GetValue.md)|Surchargé.  Retourne la valeur actuelle de la variable d'animation.|  
|[CAnimationVariable::GetVariable](../Topic/CAnimationVariable::GetVariable.md)|Retourne un pointeur à l'objet COM IUIAnimationVariable.|  
|[CAnimationVariable::SetDefaultValue](../Topic/CAnimationVariable::SetDefaultValue.md)|Définit la valeur par défaut et libère l'objet COM IUIAnimationVariable.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationVariable::SetParentAnimationObject](../Topic/CAnimationVariable::SetParentAnimationObject.md)|Définit la relation entre une variable d'animation et un objet d'animation.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationVariable::m\_bAutodestroyTransitions](../Topic/CAnimationVariable::m_bAutodestroyTransitions.md)|Indique si les objets de transition connexes doivent être supprimés.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationVariable::m\_dblDefaultValue](../Topic/CAnimationVariable::m_dblDefaultValue.md)|Spécifie la valeur par défaut propagée à IUIAnimationVariable.|  
|[CAnimationVariable::m\_lstTransitions](../Topic/CAnimationVariable::m_lstTransitions.md)|Contient une liste des transitions qui animent cette variable d'animation.|  
|[CAnimationVariable::m\_pParentObject](../Topic/CAnimationVariable::m_pParentObject.md)|Pointeur vers un objet d'animation qui encapsule cette variable d'animation.|  
|[CAnimationVariable::m\_variable](../Topic/CAnimationVariable::m_variable.md)|Stocke un pointeur à l'objet COM IUIAnimationVariable.  NULL si l'objet COM n'a pas encore été créé, ou si la création a échoué.|  
  
## Notes  
 La classe CAnimationVariable encapsule l'objet COM IUIAnimationVariable.  Contient également une liste de transitions à appliquer à la variable d'animation dans un storyboard.  Les objets CAnimationVariable sont incorporés dans les objets d'animation qui peuvent représenter dans une application une valeur animée, une point, une taille, une couleur et un rectangle.  
  
## Hiérarchie d'héritage  
 [CAnimationVariable](../../mfc/reference/canimationvariable-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)