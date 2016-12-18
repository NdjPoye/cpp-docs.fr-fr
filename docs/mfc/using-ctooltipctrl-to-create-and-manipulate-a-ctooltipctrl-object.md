---
title: "Utilisation de CToolTipCtrl pour cr&#233;er et manipuler un objet CToolTipCtrl | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CToolTipCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolTipCtrl (classe), utilisation"
  - "info-bulles (C++), créer"
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de CToolTipCtrl pour cr&#233;er et manipuler un objet CToolTipCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Voici un exemple d'utilisation de [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) :  
  
### Pour créer et manipuler un CToolTipCtrl  
  
1.  Construisez l'objet `CToolTipCtrl`.  
  
2.  Appelez [Créer](../Topic/CToolTipCtrl::Create.md) pour créer le contrôle commun d'info\-bulle windows et le joindre à l'objet `CToolTipCtrl`.  
  
3.  Appelez [AddTool](../Topic/CToolTipCtrl::AddTool.md) pour stocker un outil à l'aide du contrôle d'info\-bulle, afin que les informations stockées dans l'info\-bulle soient affichées lorsque le curseur est sur l'outil.  
  
4.  Appelez [SetToolInfo](../Topic/CToolTipCtrl::SetToolInfo.md) pour définir les informations qu'une info\-bulle contient pour un outil.  
  
5.  Appelez [SetToolRect](../Topic/CToolTipCtrl::SetToolRect.md) pour définir un nouveau rectangle englobant pour un outil.  
  
6.  Appelez [HitTest](../Topic/CToolTipCtrl::HitTest.md) pour tester un point pour déterminer s'il s'agit du rectangle englobant de l'outil donné et, le cas échéant, extraire les informations sur l'outil.  
  
7.  Appelez [GetToolCount](../Topic/CToolTipCtrl::GetToolCount.md) pour extraire un décompte des outils enregistrés avec le contrôle de l'info\-bulle.  
  
## Voir aussi  
 [Utilisation de CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)