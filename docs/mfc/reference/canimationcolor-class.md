---
title: "CAnimationColor Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimationColor"
  - "afxanimationcontroller/CAnimationColor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationColor (classe)"
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CAnimationColor Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente les fonctionnalités d'une couleur dont les composants rouge, vert et bleu peuvent être animés.  
  
## Syntaxe  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationColor::CAnimationColor](../Topic/CAnimationColor::CAnimationColor.md)|Surchargé.  Construit un objet de couleur d'animation.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationColor::AddTransition](../Topic/CAnimationColor::AddTransition.md)|Ajoute des transitions pour les composantes rouge, vert et bleu.|  
|[CAnimationColor::GetB](../Topic/CAnimationColor::GetB.md)|Fournit l'accès à CAnimationVariable qui représente la composante bleu.|  
|[CAnimationColor::GetDefaultValue](../Topic/CAnimationColor::GetDefaultValue.md)|Retourne les valeurs par défaut des composants de couleur.|  
|[CAnimationColor::GetG](../Topic/CAnimationColor::GetG.md)|Fournit l'accès à CAnimationVariable qui représente la composante vert.|  
|[CAnimationColor::GetR](../Topic/CAnimationColor::GetR.md)|Fournit l'accès à CAnimationVariable qui représente la composante rouge.|  
|[CAnimationColor::GetValue](../Topic/CAnimationColor::GetValue.md)|Renvoie la valeur actuelle.|  
|[CAnimationColor::SetDefaultValue](../Topic/CAnimationColor::SetDefaultValue.md)|Définit la valeur par défaut.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationColor::GetAnimationVariableList](../Topic/CAnimationColor::GetAnimationVariableList.md)|Insère les variables d'animation encapsulées dans une liste.  \(Substitue [CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md).\)|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationColor::operator COLORREF](../Topic/CAnimationColor::operator%20COLORREF.md)||  
|[CAnimationColor::operator\=](../Topic/CAnimationColor::operator=.md)|Assigne une couleur à CAnimationColor.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationColor::m\_bValue](../Topic/CAnimationColor::m_bValue.md)|Variable de l'animation encapsulée qui représente la composante bleu de la couleur de l'animation.|  
|[CAnimationColor::m\_gValue](../Topic/CAnimationColor::m_gValue.md)|Variable de l'animation encapsulée qui représente la composante vert de la couleur de l'animation.|  
|[CAnimationColor::m\_rValue](../Topic/CAnimationColor::m_rValue.md)|Variable de l'animation encapsulée qui représente la composante rouge de la couleur de l'animation.|  
  
## Notes  
 La classe CAnimationColor encapsule trois objets CAnimationVariable et peut représenter dans les applications une couleur.  Par exemple, vous pouvez utiliser cette classe pour animer des couleurs de n'importe quel objet sur l'écran \(comme la couleur du texte, la couleur d'arrière\-plan, etc.\).  Pour utiliser cette classe dans l'application, il suffit de créer une instance d'un objet de cette classe, de l'ajouter au contrôleur de l'animation à l'aide de CAnimationController::AddAnimationObject et d'appeler AddTransition pour chaque transition à appliquer aux composantes rouge, vert et bleu.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationColor](../../mfc/reference/canimationcolor-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)