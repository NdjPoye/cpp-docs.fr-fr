---
title: "Manipulation du contr&#244;le Progress | Microsoft Docs"
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
  - "contrôler des contrôles de progression"
  - "CProgressCtrl (classe), manipuler"
  - "CProgressCtrl (classe), utilisation"
  - "CProgressCtrl (classe), utiliser"
  - "progress (contrôles) (C++), manipuler"
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Manipulation du contr&#244;le Progress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il existe trois manières de modifier la position actuelle d'un contrôle de progression \([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)\).  
  
-   L'emplacement peut être modifiée par un montant prédéfinie d'index.  
  
-   L'emplacement peut être modifiée par une valeur arbitraire.  
  
-   L'emplacement peut être modifiée à une valeur spécifique.  
  
### Pour modifier la position par une valeur prédéfinie  
  
1.  Utilisez la fonction membre [SetStep](../Topic/CProgressCtrl::SetStep.md) pour définir la quantité d'index.  Par défaut, cette valeur est 10.  Cette valeur est généralement définie comme un des paramètres initiaux pour le contrôle.  La pas peut\-être une valeur négative.  
  
2.  Utilisez la fonction membre [StepIt](../Topic/CProgressCtrl::StepIt.md) pour incrémenter la position.  Cela entraîne le rafraichissement du contrôle.  
  
    > [!NOTE]
    >  `StepIt` provoque la position de la forme.  Par exemple, considérons une plage de 1 à 100, une étape à 20, et une position 90, `StepIt` définira à la position 10.  
  
### Pour modifier la position par une valeur aléatoire  
  
1.  Utilisez la fonction membre [OffsetPos](../Topic/CProgressCtrl::OffsetPos.md) pour modifier la position.  `OffsetPos` accepte des valeurs négatives.  
  
    > [!NOTE]
    >  `OffsetPos`, contrairement à `StepIt`, n'encapsulera pas la position.  La nouvelle position est ajustée pour rester dans la plage.  
  
### Pour modifier la position d'une valeur spécifique  
  
1.  Utilisez la fonction membre de [SetPos](../Topic/CProgressCtrl::SetPos.md) pour définir la position d'une valeur spécifique.  Si nécessaire, la nouvelle position est ajustée pour figurer dans la plage.  
  
 En général, le contrôle de progression est utilisé uniquement pour la sortie.  Pour obtenir la position actuelle sans spécifier une nouvelle valeur, utilisez [GetPos](../Topic/CProgressCtrl::GetPos.md).  
  
## Voir aussi  
 [Utilisation de CProgressCtrl](../mfc/using-cprogressctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)