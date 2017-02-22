---
title: "Classe CAnimationBaseObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationBaseObject"
  - "CAnimationBaseObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationBaseObject (classe)"
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Classe CAnimationBaseObject
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Classe de base pour tous les objets d'animation.  
  
## Syntaxe  
  
```  
class CAnimationBaseObject : public CObject;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationBaseObject::CAnimationBaseObject](../Topic/CAnimationBaseObject::CAnimationBaseObject.md)|Surchargé.  Construit un objet d'animation.|  
|[CAnimationBaseObject::~CAnimationBaseObject](../Topic/CAnimationBaseObject::~CAnimationBaseObject.md)|Le destructeur.  Appelé lorsqu'un objet d'animation est détruit.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationBaseObject::ApplyTransitions](../Topic/CAnimationBaseObject::ApplyTransitions.md)|Ajoute des transitions au storyboard avec une variable d'animation encapsulée.|  
|[CAnimationBaseObject::ClearTransitions](../Topic/CAnimationBaseObject::ClearTransitions.md)|Supprime toutes les transitions connexes.|  
|[CAnimationBaseObject::ContainsVariable](../Topic/CAnimationBaseObject::ContainsVariable.md)|Détermine si un objet d'animation contient une variable d'animation particulière.|  
|[CAnimationBaseObject::CreateTransitions](../Topic/CAnimationBaseObject::CreateTransitions.md)|Crée des transitions associées à un objet d'animation.|  
|[CAnimationBaseObject::DetachFromController](../Topic/CAnimationBaseObject::DetachFromController.md)|Détache un objet d'animation du contrôleur de l'animation parent.|  
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](../Topic/CAnimationBaseObject::EnableIntegerValueChangedEvent.md)|Configure le gestionnaire d'événements Valeur de type entier modifié.|  
|[CAnimationBaseObject::EnableValueChangedEvent](../Topic/CAnimationBaseObject::EnableValueChangedEvent.md)|Configure le gestionnaire d'événements Valeur modifié.|  
|[CAnimationBaseObject::GetAutodestroyTransitions](../Topic/CAnimationBaseObject::GetAutodestroyTransitions.md)|Indique si la transition connexe est détruite automatiquement.|  
|[CAnimationBaseObject::GetGroupID](../Topic/CAnimationBaseObject::GetGroupID.md)|Retourne l'ID de groupe actuel.|  
|[CAnimationBaseObject::GetObjectID](../Topic/CAnimationBaseObject::GetObjectID.md)|Retourne l'ID de l'objet actif.|  
|[CAnimationBaseObject::GetUserData](../Topic/CAnimationBaseObject::GetUserData.md)|Retourne les données définies par l'utilisateur.|  
|[CAnimationBaseObject::SetAutodestroyTransitions](../Topic/CAnimationBaseObject::SetAutodestroyTransitions.md)|Définit un indicateur qui ordonne la destruction automatique des transitions.|  
|[CAnimationBaseObject::SetID](../Topic/CAnimationBaseObject::SetID.md)|Définit de nouveaux ID.|  
|[CAnimationBaseObject::SetUserData](../Topic/CAnimationBaseObject::SetUserData.md)|Définit les données définies par l'utilisateur.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md)|Collecte des pointeurs aux variables de l'animation contenues.|  
|[CAnimationBaseObject::SetParentAnimationObjects](../Topic/CAnimationBaseObject::SetParentAnimationObjects.md)|Établit une relation entre les variables d'animation contenues dans un objet d'animation et leur conteneur.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationBaseObject::m\_bAutodestroyTransitions](../Topic/CAnimationBaseObject::m_bAutodestroyTransitions.md)|Indique si les transitions connexes doivent être détruites automatiquement.|  
|[CAnimationBaseObject::m\_dwUserData](../Topic/CAnimationBaseObject::m_dwUserData.md)|Stocke les données définies par l'utilisateur.|  
|[CAnimationBaseObject::m\_nGroupID](../Topic/CAnimationBaseObject::m_nGroupID.md)|Spécifie l'ID de groupe de l'objet d'animation.|  
|[CAnimationBaseObject::m\_nObjectID](../Topic/CAnimationBaseObject::m_nObjectID.md)|Spécifie l'ID d'objet de l'objet d'animation.|  
|[CAnimationBaseObject::m\_pParentController](../Topic/CAnimationBaseObject::m_pParentController.md)|Pointeur vers un contrôleur d'animation parent.|  
  
## Notes  
 Cette classe implémente des méthodes de base pour tous les objets d'animation.  Un objet d'animation peut représenter une valeur, un point, une taille, un rectangle ou une couleur dans une application, ainsi que toute entité personnalisée.  Les objets d'animation sont stockés dans les groupes d'animation \(voir CAnimationGroup\).  Chaque groupe peut être animé séparément et peut être traité comme un équivalent du storyboard.  Un objet d'animation encapsule une ou plusieurs variables d'animation \(voir CAnimationVariable\), en fonction de sa représentation logique.  Par exemple, CAnimationRect contient quatre variables d'animation \- une variable pour chaque côté du rectangle.  Chaque classe d'objet d'animation expose la méthode AddTransition surchargée, qui doit être utilisée pour appliquer des transitions aux variables d'animation encapsulées.  Un objet d'animation peut être identifié par l'ID d'objet \(éventuellement\) et par l'ID de groupe.  Un ID de groupe est nécessaire pour placer un objet d'animation dans le groupe approprié, mais si un ID de groupe n'est pas spécifié, l'objet est placé dans le groupe par défaut dont l'ID est 0.  Si vous appelez SetID avec un GroupID différent, un objet d'animation est déplacé vers un autre groupe \(un nouveau groupe est créé si nécessaire\).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)