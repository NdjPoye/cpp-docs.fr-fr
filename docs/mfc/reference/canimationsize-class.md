---
title: "Classe CAnimationSize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationSize"
  - "CAnimationSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationSize (classe)"
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Classe CAnimationSize
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente les fonctionnalités d'un objet taille dont les dimensions peuvent être animées.  
  
## Syntaxe  
  
```  
class CAnimationSize : public CAnimationBaseObject;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationSize::CAnimationSize](../Topic/CAnimationSize::CAnimationSize.md)|Surchargé.  Construit un objet d'animation taille.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationSize::AddTransition](../Topic/CAnimationSize::AddTransition.md)|Ajoute des transitions pour la largeur et la hauteur.|  
|[CAnimationSize::GetCX](../Topic/CAnimationSize::GetCX.md)|Fournit l'accès à CAnimationVariable qui représente la largeur.|  
|[CAnimationSize::GetCY](../Topic/CAnimationSize::GetCY.md)|Fournit l'accès à CAnimationVariable qui représente la hauteur.|  
|[CAnimationSize::GetDefaultValue](../Topic/CAnimationSize::GetDefaultValue.md)|Retourne les valeurs par défaut de la largeur et de la hauteur.|  
|[CAnimationSize::GetValue](../Topic/CAnimationSize::GetValue.md)|Renvoie la valeur actuelle.|  
|[CAnimationSize::SetDefaultValue](../Topic/CAnimationSize::SetDefaultValue.md)|Définit la valeur par défaut.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationSize::GetAnimationVariableList](../Topic/CAnimationSize::GetAnimationVariableList.md)|Insère les variables d'animation encapsulées dans une liste.  \(Substitue [CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md).\)|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationSize::operator CSize](../Topic/CAnimationSize::operator%20CSize.md)|Convertit CAnimationSize en objet CSize.|  
|[CAnimationSize::operator\=](../Topic/CAnimationSize::operator=.md)|Assigne szSrc à CAnimationSize.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationSize::m\_cxValue](../Topic/CAnimationSize::m_cxValue.md)|Variable de l'animation encapsulée qui représente la largeur de la taille de l'animation.|  
|[CAnimationSize::m\_cyValue](../Topic/CAnimationSize::m_cyValue.md)|Variable de l'animation encapsulée qui représente la hauteur de la taille de l'animation.|  
  
## Notes  
 La classe CAnimationSize encapsule deux objets CAnimationVariable et peut représenter dans les applications une taille.  Par exemple, vous pouvez utiliser cette classe pour animer une taille de n'importe quel objet bidimensionnel sur l'écran \(comme un rectangle, un contrôle, etc.\).  Pour utiliser cette classe dans l'application, il suffit de créer une instance d'un objet de cette classe, de l'ajouter au contrôleur de l'animation à l'aide de CAnimationController::AddAnimationObject et d'appeler AddTransition pour chaque transition à appliquer à la largeur et\/ou hauteur.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationSize](../../mfc/reference/canimationsize-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)