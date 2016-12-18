---
title: "Classe CCustomTransition | Microsoft Docs"
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
  - "afxanimationcontroller/CCustomTransition"
  - "CCustomTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCustomTransition (classe)"
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CCustomTransition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente une transition personnalisée.  
  
## Syntaxe  
  
```  
class CCustomTransition : public CBaseTransition;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CCustomTransition::CCustomTransition](../Topic/CCustomTransition::CCustomTransition.md)|Construit un objet de transition personnalisé.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CCustomTransition::Create](../Topic/CCustomTransition::Create.md)|Appelle la bibliothèque des transitions pour créer l'objet COM de la transition encapsulé.  \(Substitue [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
|[CCustomTransition::SetInitialValue](../Topic/CCustomTransition::SetInitialValue.md)|Définit une valeur initiale qui doit être appliquée à une variable d'animation associée à cette transition.|  
|[CCustomTransition::SetInitialVelocity](../Topic/CCustomTransition::SetInitialVelocity.md)|Définit une rapidité initiale qui doit être appliquée à une variable d'animation associée à cette transition.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CCustomTransition::m\_bInitialValueSpecified](../Topic/CCustomTransition::m_bInitialValueSpecified.md)|Indique si la valeur initiale a été spécifiée avec SetInitialValue.|  
|[CCustomTransition::m\_bInitialVelocitySpecified](../Topic/CCustomTransition::m_bInitialVelocitySpecified.md)|Indique si la rapidité initiale a été spécifiée avec SetInitialVelocity.|  
|[CCustomTransition::m\_initialValue](../Topic/CCustomTransition::m_initialValue.md)|Stocke la valeur initiale.|  
|[CCustomTransition::m\_initialVelocity](../Topic/CCustomTransition::m_initialVelocity.md)|Stocke la rapidité initiale.|  
|[CCustomTransition::m\_pInterpolator](../Topic/CCustomTransition::m_pInterpolator.md)|Stocke un pointeur à un interpolateur personnalisé.|  
  
## Notes  
 La classe CCustomTransitions permet aux développeurs d'implémenter des transitions personnalisées.  Il est créé et utilisé comme une transition standard, mais son constructeur accepte comme paramètre un pointeur à un interpolateur personnalisé.  Exécutez les étapes suivantes pour utiliser les transitions personnalisées : 1.  Dérivez une classe de CCustomInterpolator implémentez au moins une méthode InterpolateValue.  2.  Vérifiez que la durée de vie de l'objet de l'interpolateur personnalisé est plus longue que la durée d'animation où il est utilisé.  3.  Crée l'instance \(avec l'opérateur new\) d'un objet CCustomTransition et transmet un pointeur à l'interpolateur personnalisé dans le constructeur.  4.  Appelez CCustomTransition::SetInitialValue et CCustomTransition::SetInitialVelocity si ces paramètres sont requis pour l'interpolation personnalisée.  5.  Transmettez le pointeur à la transition personnalisée à la méthode AddTransition de l'objet d'animation dont la valeur doit être animée avec l'algorithme personnalisé.  6.  Lorsque la valeur de l'objet d'animation change, l'API Windows Animation appelle InterpolateValue \(et d'autres méthodes pertinentes\) dans CCustomInterpolator.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CCustomTransition](../../mfc/reference/ccustomtransition-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)