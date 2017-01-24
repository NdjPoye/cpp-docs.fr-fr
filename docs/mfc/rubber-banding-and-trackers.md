---
title: "Bande &#233;lastique et dispositifs de suivi | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRectTracker (classe), implémenter des dispositifs de suivi"
  - "objets OLE, sélectionner"
  - "bande élastique"
  - "dispositifs de suivi"
  - "WM_LBUTTONDOWN"
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Bande &#233;lastique et dispositifs de suivi
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une autre fonctionnalité fournie avec des dispositifs de suivi est la sélection "élastique", qui permet à un utilisateur de sélectionner plusieurs éléments OLE en faisant glisser un rectangle de dimensionnement autour de les éléments à sélectionner.  Lorsque l'utilisateur libère le bouton droit de la souris, les éléments dans la zone sélectionnée par l'utilisateur sont sélectionnés et peuvent être manipulés par l'utilisateur.  Par exemple, l'utilisateur peut faire glisser la sélection dans une autre application conteneur.  
  
 Implémenter cette fonctionnalité nécessite un code supplémentaire dans la fonction gestionnaire `WM_LBUTTONDOWN` de votre application.  
  
 L'exemple de code suivant implémente la sélection élastique et des fonctionnalités supplémentaires.  
  
 [!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/CPP/rubber-banding-and-trackers_1.cpp)]  
  
 Si vous souhaitez autoriser l'orientation réversible du dispositif de suivi de l'étirement, vous devez appeler [CRectTracker::TrackRubberBand](../Topic/CRectTracker::TrackRubberBand.md) avec le troisième paramètre à **TRUE**.  N'oubliez pas qu'autoriser l'orientation réversible provoquera parfois l'inversion de [CRectTracker::m\_rect](../Topic/CRectTracker::m_rect.md).  Cela peut être corrigée par un appel à [CRect::NormalizeRect](../Topic/CRect::NormalizeRect.md).  
  
 Pour plus d'informations, consultez [Éléments client de conteneur](../mfc/containers-client-items.md) et [Personnaliser le glisser\-déplacer](../mfc/drag-and-drop-customizing.md).  
  
## Voir aussi  
 [Dispositifs de suivi : implémentation de dispositifs de suivi dans votre application OLE](../mfc/trackers-implementing-trackers-in-your-ole-application.md)   
 [CRectTracker Class](../mfc/reference/crecttracker-class.md)