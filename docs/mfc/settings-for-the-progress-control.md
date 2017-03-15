---
title: "Param&#232;tres du contr&#244;le Progress | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CProgressCtrl (classe), paramètres"
  - "progress (contrôles) (C++), paramètres"
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Param&#232;tres du contr&#244;le Progress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les paramètres de base du contrôle de progression \([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)\) sont la plage et la position actuelle.  L'étendue représente la durée entière de l'opération.  La propriété  représente la progression de l'application dans l'achèvement de l'opération.  Toute modification à la plage ou à l'origine de la position le contrôle de progression de rafraîchir.  
  
 Par défaut, la plage est définie sur 0 et 100, et la position de départ est défini à 0.  Pour récupérer les paramètres actuels de plage pour le contrôle de progression, utilisez la fonction membre d'[GetRange](../Topic/CProgressCtrl::GetRange.md).  Pour modifier la plage, utilisez la fonction membre d'[SetRange](../Topic/CProgressCtrl::SetRange.md).  
  
 Pour définir la position, utilisez [SetPos](../Topic/CProgressCtrl::SetPos.md).  Pour obtenir la position actuelle sans spécifier une nouvelle valeur, utilisez [GetPos](../Topic/CProgressCtrl::GetPos.md).  Par exemple, vous pouvez rechercher simplement sur l'état de l'opération en cours.  
  
 Pour effectuer un pas l'emplacement actuel du contrôle de progression, utilisez [StepIt](../Topic/CProgressCtrl::StepIt.md).  Pour définir la quantité de chaque étape, utilisez [SetStep](../Topic/CProgressCtrl::SetStep.md)  
  
## Voir aussi  
 [Utilisation de CProgressCtrl](../mfc/using-cprogressctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)