---
title: "Classe CAnimationRect | Microsoft Docs"
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
  - "CAnimationRect"
  - "afxanimationcontroller/CAnimationRect"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationRect (classe)"
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CAnimationRect
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente les fonctionnalités d'un rectangle dont les côtés peuvent être animés.  
  
## Syntaxe  
  
```  
class CAnimationRect : public CAnimationBaseObject;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationRect::CAnimationRect](../Topic/CAnimationRect::CAnimationRect.md)|Surchargé.  Construit un objet d'animation rect.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationRect::AddTransition](../Topic/CAnimationRect::AddTransition.md)|Ajoute des transitions pour les coordonnées gauche, supérieure, droite et inférieure.|  
|[CAnimationRect::GetBottom](../Topic/CAnimationRect::GetBottom.md)|Fournit l'accès à CAnimationVariable qui représente la coordonnée inférieure.|  
|[CAnimationRect::GetDefaultValue](../Topic/CAnimationRect::GetDefaultValue.md)|Retourne les valeurs par défaut des limites du rectangle.|  
|[CAnimationRect::GetLeft](../Topic/CAnimationRect::GetLeft.md)|Fournit l'accès à CAnimationVariable qui représente la coordonnée gauche.|  
|[CAnimationRect::GetRight](../Topic/CAnimationRect::GetRight.md)|Fournit l'accès à CAnimationVariable qui représente la coordonnée droite.|  
|[CAnimationRect::GetTop](../Topic/CAnimationRect::GetTop.md)|Fournit l'accès à CAnimationVariable qui représente la coordonnée supérieure.|  
|[CAnimationRect::GetValue](../Topic/CAnimationRect::GetValue.md)|Renvoie la valeur actuelle.|  
|[CAnimationRect::SetDefaultValue](../Topic/CAnimationRect::SetDefaultValue.md)|Définit la valeur par défaut.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationRect::GetAnimationVariableList](../Topic/CAnimationRect::GetAnimationVariableList.md)|Insère les variables d'animation encapsulées dans une liste.  \(Substitue [CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md).\)|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationRect::operator RECT](../Topic/CAnimationRect::operator%20RECT.md)|Convertit CAnimationRect en objet RECT.|  
|[CAnimationRect::operator\=](../Topic/CAnimationRect::operator=.md)|Assigne rect à CAnimationRect.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationRect::m\_bFixedSize](../Topic/CAnimationRect::m_bFixedSize.md)|Indique si le rectangle a une taille fixe.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationRect::m\_bottomValue](../Topic/CAnimationRect::m_bottomValue.md)|Variable de l'animation encapsulée qui représente la limite inférieure du rectangle de l'animation.|  
|[CAnimationRect::m\_leftValue](../Topic/CAnimationRect::m_leftValue.md)|Variable de l'animation encapsulée qui représente la limite gauche du rectangle de l'animation.|  
|[CAnimationRect::m\_rightValue](../Topic/CAnimationRect::m_rightValue.md)|Variable de l'animation encapsulée qui représente la limite droite du rectangle de l'animation.|  
|[CAnimationRect::m\_szInitial](../Topic/CAnimationRect::m_szInitial.md)|Spécifie la taille initiale du rectangle d'animation.|  
|[CAnimationRect::m\_topValue](../Topic/CAnimationRect::m_topValue.md)|Variable de l'animation encapsulée qui représente la limite supérieure du rectangle de l'animation.|  
  
## Notes  
 La classe CAnimationRect encapsule quatre objets CAnimationVariable et peut représenter dans les applications un rectangle.  Pour utiliser cette classe dans l'application, il suffit de créer une instance d'un objet de cette classe, de l'ajouter au contrôleur de l'animation à l'aide de CAnimationController::AddAnimationObject et d'appeler AddTransition pour chaque transition à appliquer aux coordonnées gauche, droit, haut et bas.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationRect](../../mfc/reference/canimationrect-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)