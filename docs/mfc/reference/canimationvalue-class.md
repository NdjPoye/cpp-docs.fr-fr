---
title: "Classe CAnimationValue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationValue"
  - "CAnimationValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationValue (classe)"
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Classe CAnimationValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente les fonctionnalités d'un objet d'animation qui a une valeur.  
  
## Syntaxe  
  
```  
class CAnimationValue : public CAnimationBaseObject;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationValue::CAnimationValue](../Topic/CAnimationValue::CAnimationValue.md)|Surchargé.  Construit un objet CAnimationValue.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationValue::AddTransition](../Topic/CAnimationValue::AddTransition.md)|Ajoute une transition à appliquer à une valeur.|  
|[CAnimationValue::GetValue](../Topic/CAnimationValue::GetValue.md)|Surchargé.  Extrait la valeur actuelle.|  
|[CAnimationValue::GetVariable](../Topic/CAnimationValue::GetVariable.md)|Fournit l'accès à la variable d'animation encapsulée.|  
|[CAnimationValue::SetDefaultValue](../Topic/CAnimationValue::SetDefaultValue.md)|Définit la valeur par défaut.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationValue::GetAnimationVariableList](../Topic/CAnimationValue::GetAnimationVariableList.md)|Insère la variable d'animation encapsulée dans une liste.  \(Substitue [CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md).\)|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationValue::operator DOUBLE](../Topic/CAnimationValue::operator%20DOUBLE.md)|Fournit la conversion entre CAnimationValue et DOUBLE.|  
|[CAnimationValue::operator INT32](../Topic/CAnimationValue::operator%20INT32.md)|Fournit la conversion entre CAnimationValue et INT32.|  
|[CAnimationValue::operator\=](../Topic/CAnimationValue::operator=.md)|Surchargé.  Assigne une valeur INT32 à CAnimationValue.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationValue::m\_value](../Topic/CAnimationValue::m_value.md)|Variable de l'animation encapsulée qui représente la valeur d'animation.|  
  
## Notes  
 La classe CAnimationValue encapsule un objet CAnimationVariable unique et peut représenter dans les applications une valeur animée unique.  Par exemple, vous pouvez utiliser cette classe pour la transparence animée \(effet d'atténuation\), l'angle \(faire pivoter des objets\) ou dans n'importe quel autre cas où vous devez créer une animation en fonction d'une valeur animée unique.  Pour utiliser cette classe dans l'application, il suffit de créer une instance d'un objet de cette classe, de l'ajouter au contrôleur de l'animation à l'aide de CAnimationController::AddAnimationObject et d'appeler AddTransition pour chaque transition à appliquer à la valeur.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationValue](../../mfc/reference/canimationvalue-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)