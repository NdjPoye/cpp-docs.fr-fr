---
title: "Styles de contr&#244;le Slider | Microsoft Docs"
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
  - "CSliderCtrl (classe), styles"
  - "contrôles Slider, styles"
  - "styles, CSliderCtrl"
  - "styles, contrôles Slider"
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Styles de contr&#244;le Slider
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les contrôles de curseur \([CSliderCtrl](../mfc/reference/csliderctrl-class.md)\) peuvent avoir une orientation verticale ou horizontale.  Ils peuvent contenir des graduations de chaque côté, les deux parties, ou ni l'un ni l'autre.  Ils peuvent également être utilisés pour spécifier une plage de valeurs consécutives.  Ces propriétés sont contrôlées en utilisant des styles de curseur, que vous spécifiez lors de la création du curseur.  
  
 Les styles `TBS_HORZ` et `TBS_VERT` déterminent l'orientation du curseur.  Si vous ne spécifiez pas une orientation, le curseur est orienté horizontalement.  
  
 Le style `TBS_AUTOTICKS` crée un curseur qui a une graduation pour chaque incrément dans sa plage de valeurs.  Ces graduations sont ajoutées automatiquement lorsque vous appelez la fonction membre [SetRange](../Topic/CSliderCtrl::SetRange.md).  Si vous ne spécifiez pas `TBS_AUTOTICKS`, vous pouvez utiliser des fonctions membres, telles que [SetTic](../Topic/CSliderCtrl::SetTic.md) et [SetTicFreq](../Topic/CSliderCtrl::SetTicFreq.md), pour spécifier les positions des graduations.  Pour créer un curseur qui n'affiche pas les graduations, vous pouvez utiliser le style d`TBS_NOTICKS`.  
  
 Vous pouvez afficher les graduations le ou des deux côtés du curseur.  Pour les contrôles Slider horizontal, vous pouvez spécifier le style `TBS_BOTTOM` ou `TBS_TOP`.  Pour les contrôles Slider horizontal, vous pouvez spécifier le style `TBS_RIGHT` ou `TBS_LEFT`. Les valeurs par défaut sont `TBS_BOTTOM` et `TBS_RIGHT`. Pour les graduations des deux côtés du contrôle Slider dans n'importe quelle orientation, spécifiez le style `TBS_BOTH`.  
  
 Un curseur peut afficher une plage de sélection que si vous spécifiez le style `TBS_ENABLESELRANGE` lorsque vous la créez.  Lorsqu'un curseur est le style, les graduations aux positions de début et de fin d'une plage de sélection sont affichées comme des triangles \(au lieu des tirets vertical\) et la plage de sélection est mise en surbrillance.  Par exemple, les plages de sélection peuvent être utiles pour une application de planification.  L'utilisateur peut sélectionner une plage des graduations qui correspondent aux heures dans un jour pour identifier une heure de réunion planifiée.  
  
 Par défaut, la longueur du curseur dans un curseur varie comme la plage de sélection change.  Si le curseur a le style de **TBS\_FIXEDLENGTH**, la longueur du curseur reste la même même si la plage de sélection change.  Un curseur qui a le style de **TBS\_NOTHUMB** n'inclut pas de curseur.  
  
## Voir aussi  
 [Utilisation de CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)