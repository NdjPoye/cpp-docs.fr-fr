---
title: "Classe CCustomInterpolator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CCustomInterpolator"
  - "CCustomInterpolator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCustomInterpolator (classe)"
ms.assetid: 28d85595-989a-40a3-b003-e0e38437a94d
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Classe CCustomInterpolator
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente une interclasseuse de base.  
  
## Syntaxe  
  
```  
class CCustomInterpolator;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CCustomInterpolator::CCustomInterpolator](../Topic/CCustomInterpolator::CCustomInterpolator.md)|Surchargé.  Construit un objet de l'interpolateur personnalisé et initialise la durée et la rapidité sur les valeurs spécifiées.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CCustomInterpolator::GetDependencies](../Topic/CCustomInterpolator::GetDependencies.md)|Obtient les dépendances de l'interpolateur.|  
|[CCustomInterpolator::GetDuration](../Topic/CCustomInterpolator::GetDuration.md)|Obtient la durée de l'interpolateur.|  
|[CCustomInterpolator::GetFinalValue](../Topic/CCustomInterpolator::GetFinalValue.md)|Obtient la valeur finale obtenue par l'interpolateur.|  
|[CCustomInterpolator::Init](../Topic/CCustomInterpolator::Init.md)|Initialise la durée et la valeur finale.|  
|[CCustomInterpolator::InterpolateValue](../Topic/CCustomInterpolator::InterpolateValue.md)|Interpole la valeur à un offset donné.|  
|[CCustomInterpolator::InterpolateVelocity](../Topic/CCustomInterpolator::InterpolateVelocity.md)|Interpole la rapidité à un offset donné|  
|[CCustomInterpolator::SetDuration](../Topic/CCustomInterpolator::SetDuration.md)|Définit la durée de l'interpolateur.|  
|[CCustomInterpolator::SetInitialValueAndVelocity](../Topic/CCustomInterpolator::SetInitialValueAndVelocity.md)|Définit la valeur initiale de l'interpolateur et la rapidité.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CCustomInterpolator::m\_currentValue](../Topic/CCustomInterpolator::m_currentValue.md)|La valeur interpolée.|  
|[CCustomInterpolator::m\_currentVelocity](../Topic/CCustomInterpolator::m_currentVelocity.md)|Rapidité interpolée.|  
|[CCustomInterpolator::m\_duration](../Topic/CCustomInterpolator::m_duration.md)|Durée de la transition.|  
|[CCustomInterpolator::m\_finalValue](../Topic/CCustomInterpolator::m_finalValue.md)|Valeur finale d'une variable à la fin de la transition.|  
|[CCustomInterpolator::m\_initialValue](../Topic/CCustomInterpolator::m_initialValue.md)|Valeur de la variable au début de la transition.|  
|[CCustomInterpolator::m\_initialVelocity](../Topic/CCustomInterpolator::m_initialVelocity.md)|Rapidité de la variable au début de la transition.|  
  
## Notes  
 Dérivez une classe de CCustomInterpolator et remplacez toutes les méthodes nécessaires pour implémenter un algorithme d'interpolation personnalisé.  Un pointeur vers cette classe doit être passé comme un paramètre à CCustomTransition.  
  
## Hiérarchie d'héritage  
 [CCustomInterpolator](../../mfc/reference/ccustominterpolator-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)