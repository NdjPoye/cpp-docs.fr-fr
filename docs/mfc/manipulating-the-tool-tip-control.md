---
title: "Manipulation du contr&#244;le d&#39;info-bulle | Microsoft Docs"
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
  - "CToolTipCtrl (classe), manipuler les attributs des astuces"
  - "info-bulles (C++), attributs"
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Manipulation du contr&#244;le d&#39;info-bulle
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe `CToolTipCtrl` fournit un groupe de méthodes qui contrôlent les différents attributs de l'objet `CToolTipCtrl` et la fenêtre d'info\-bulle.  
  
 Les durées initiale, de popup et de réapparition pour les fenêtres d'info\-bulle peuvent être définies et récupérées avec des appels à [GetDelayTime](../Topic/CToolTipCtrl::GetDelayTime.md) et [SetDelayTime](../Topic/CToolTipCtrl::SetDelayTime.md).  
  
 Modifier l'apparence des fenêtres d'info\-bulle avec les fonctions suivantes :  
  
-   [GetMargin](../Topic/CToolTipCtrl::GetMargin.md) et [SetMargin](../Topic/CToolTipCtrl::SetMargin.md) Récupère et définit la largeur entre la bordure d'info\-bulle et le texte d'info\-bulle.  
  
-   [GetMaxTipWidth](../Topic/CToolTipCtrl::GetMaxTipWidth.md) et [SetMaxTipWidth](../Topic/CToolTipCtrl::SetMaxTipWidth.md) Récupère et définit la largeur maximale de la fenêtre d'info\-bulle.  
  
-   [GetTipBkColor](../Topic/CToolTipCtrl::GetTipBkColor.md) et [SetTipBkColor](../Topic/CToolTipCtrl::SetTipBkColor.md) Récupère et définit la couleur d'arrière\-plan de la fenêtre d'info\-bulle.  
  
-   [GetTipTextColor](../Topic/CToolTipCtrl::GetTipTextColor.md) et [SetTipTextColor](../Topic/CToolTipCtrl::SetTipTextColor.md) Récupère et définit la couleur du texte de la fenêtre d'info\-bulle.  
  
 Pour que le contrôle d'info\-bulle soit notifié des messages importants, par exemple des messages **WM\_LBUTTONXXX**, vous devez relayer les messages à votre contrôle d'info\-bulle.  La meilleure méthode pour le relai consiste à effectuer un appel à [CToolTipCtrl::RelayEvent](../Topic/CToolTipCtrl::RelayEvent.md), dans la fonction `PreTranslateMessage` de la fenêtre propriétaire.  L'exemple suivant illustre une méthode possible \(supposant que le contrôle d'info\-bulle est appelé `m_ToolTip`\) :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#41](../mfc/codesnippet/CPP/manipulating-the-tool-tip-control_1.cpp)]  
  
 Pour supprimer immédiatement une fenêtre d'info\-bulle, appelez la méthode [Pop](../Topic/CToolTipCtrl::Pop.md).  
  
## Voir aussi  
 [Utilisation de CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)