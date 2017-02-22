---
title: "Param&#232;tres du contr&#244;le d’info-bulle | Microsoft Docs"
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
  - "info-bulles [C++], activer"
  - "Classe CToolTipCtrl, paramètres"
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Param&#232;tres du contr&#244;le d’info-bulle
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez définir le contrôle d’info\-bulle \([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)\) de sorte qu’il soit actif ou inactif. Quand vous le définissez comme étant actif, le contrôle d’info\-bulle s’affiche quand le curseur se trouve sur un outil. Quand vous le définissez comme étant inactif, le contrôle d’info\-bulle ne s’affiche pas, même si le curseur se trouve sur un outil. Appelez [Activate](../Topic/CToolTipCtrl::Activate.md) pour activer ou désactiver un contrôle d’info\-bulle.  
  
 Vous pouvez définir une info\-bulle active pour qu’elle s’affiche quand le curseur se trouve sur un outil, que la fenêtre propriétaire du contrôle d’info\-bulle soit active ou inactive, en utilisant le style **TTS\_ALWAYSTIP**. Si vous n’utilisez pas ce style, le contrôle d’info\-bulle s’affiche quand la fenêtre de propriétaire de l’outil est active, mais pas quand elle est inactive.  
  
 La plupart des applications contiennent des barres d’outils qui correspondent à des commandes de menu. Pour ces outils, il est pratique que le contrôle d’info\-bulle affiche le même texte que l’élément de menu correspondant. Le système supprime automatiquement les caractères de raccourci « & » \(esperluette\) de toutes les chaînes passées à un contrôle d’info\-bulle, sauf si le contrôle a le style **TTS\_NOPREFIX**.  
  
## Voir aussi  
 [Utilisation de CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)