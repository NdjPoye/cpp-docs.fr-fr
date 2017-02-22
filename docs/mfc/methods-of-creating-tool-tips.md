---
title: "M&#233;thodes de cr&#233;ation d&#39;info-bulles | Microsoft Docs"
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
  - "CToolTipCtrl (classe), créer des info-bulles"
  - "info-bulles (C++), créer"
  - "info-bulles (C++), info-bulles"
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# M&#233;thodes de cr&#233;ation d&#39;info-bulles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC fournit trois classes pour créer et gérer le contrôle d'info\-bulle : [CWnd](../mfc/reference/cwnd-class.md), [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md), [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) et [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md).  Les fonctions membres d'info\-bulle de ces classes encapsulent l'API de contrôle commun Windows.  La classe `CToolBarCtrl` et la classe sont dérivées `CToolTipCtrl` de la classe `CWnd`.  
  
 `CWnd` fournit quatre fonctions membres pour créer et gérer des info\-bulles : [EnableToolTips](../Topic/CWnd::EnableToolTips.md), [CancelToolTips](../Topic/CWnd::CancelToolTips.md), [FilterToolTipMessage](../Topic/CWnd::FilterToolTipMessage.md), et [OnToolHitTest](../Topic/CWnd::OnToolHitTest.md).  Consultez les différentes fonctions membre pour plus d'informations sur la façon dont elles mettent en œuvre les info\-bulles.  
  
 Si vous créez une barre d'outils en utilisant `CToolBarCtrl`, vous pouvez implémenter des info\-bulles pour la barre d'outils en utilisant directement les fonctions membres suivantes : [GetToolTips](../Topic/CToolBarCtrl::GetToolTips.md) et [SetToolTips](../Topic/CToolBarCtrl::SetToolTips.md).  Consultez ces différentes fonctions de membre et [Notifications d'Info\-bulle de gestion](../mfc/handling-tool-tip-notifications.md) pour plus d'informations sur la façon dont elles mettent en œuvre des info\-bulles.  
  
 La classe `CToolTipCtrl` fournit les fonctionnalités du contrôle commun d'info\-bulle Windows.  Un seul contrôle d'info\-bulle peut fournir des informations pour plusieurs outils.  Un outil est une fenêtre, telle qu'une fenêtre enfant ou un contrôle, ou d'une zone rectangulaire définie par l'application dans une zone client de la fenêtre.  La classe [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md) dérive de `CToolTipCtrl` et fournit des styles visuels supplémentaires et des fonctionnalités.  
  
## Voir aussi  
 [Utilisation de CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)