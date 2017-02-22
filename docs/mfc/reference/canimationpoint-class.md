---
title: "Classe CAnimationPoint | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimationPoint"
  - "afxanimationcontroller/CAnimationPoint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationPoint (classe)"
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Classe CAnimationPoint
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente les fonctionnalités d'un point dont les coordonnées peuvent être animées.  
  
## Syntaxe  
  
```  
class CAnimationPoint : public CAnimationBaseObject;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationPoint::CAnimationPoint](../Topic/CAnimationPoint::CAnimationPoint.md)|Surchargé.  Construit un objet CAnimationPoint.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationPoint::AddTransition](../Topic/CAnimationPoint::AddTransition.md)|Ajoute des transitions pour les coordonnées X et Y.|  
|[CAnimationPoint::GetDefaultValue](../Topic/CAnimationPoint::GetDefaultValue.md)|Retourne les valeurs par défaut des coordonnées X et Y.|  
|[CAnimationPoint::GetValue](../Topic/CAnimationPoint::GetValue.md)|Renvoie la valeur actuelle.|  
|[CAnimationPoint::GetX](../Topic/CAnimationPoint::GetX.md)|Fournit l'accès à CAnimationVariable pour la coordonnée X.|  
|[CAnimationPoint::GetY](../Topic/CAnimationPoint::GetY.md)|Fournit l'accès à CAnimationVariable pour la coordonnée Y.|  
|[CAnimationPoint::SetDefaultValue](../Topic/CAnimationPoint::SetDefaultValue.md)|Définit la valeur par défaut.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationPoint::GetAnimationVariableList](../Topic/CAnimationPoint::GetAnimationVariableList.md)|Insère les variables d'animation encapsulées dans une liste.  \(Substitue [CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md).\)|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationPoint::operator CPoint](../Topic/CAnimationPoint::operator%20CPoint.md)|Convertit CAnimationPoint en objet CPoint.|  
|[CAnimationPoint::operator\=](../Topic/CAnimationPoint::operator=.md)|Assigne ptSrc à CAnimationPoint.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationPoint::m\_xValue](../Topic/CAnimationPoint::m_xValue.md)|La variable de l'animation encapsulée qui représente la coordonnée X du point de l'animation.|  
|[CAnimationPoint::m\_yValue](../Topic/CAnimationPoint::m_yValue.md)|La variable de l'animation encapsulée qui représente la coordonnée Y du point de l'animation.|  
  
## Notes  
 La classe CAnimationPoint encapsule deux objets CAnimationVariable et peut représenter dans les applications un point.  Par exemple, vous pouvez utiliser cette classe pour animer une position d'un objet sur l'écran \(comme une chaîne de caractères, un cercle, un point, etc.\).  Pour utiliser cette classe dans l'application, il suffit de créer une instance d'un objet de cette classe, de l'ajouter au contrôleur de l'animation à l'aide de CAnimationController::AddAnimationObject et d'appeler AddTransition pour chaque transition à appliquer aux coordonnées X et\/ou Y.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationPoint](../../mfc/reference/canimationpoint-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)