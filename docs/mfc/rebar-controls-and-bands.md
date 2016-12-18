---
title: "Contr&#244;les rebar et bandes | Microsoft Docs"
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
  - "bandes, dans les contrôles rebar"
  - "rebar (contrôles), utiliser des bandes dans"
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les rebar et bandes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'objectif principal d'un contrôle rebar consiste à faire office de conteneur pour les fenêtres enfants, les contrôles de la boîte de dialogue communes, menus, les barres d'outils, et ainsi de suite.  Cette relation contenant\-contenu est prise en charge par le concept d'une « tape ». Chaque bande rebar peut contenir toute combinaison d'une barre à pinces, une bitmap, d'une étiquette de texte, et la fenêtre enfant.  
  
 La classe `CReBarCtrl` a de nombreuses fonctions membres que vous pouvez utiliser pour récupérer, et manipuler, les informations sur une bande rebar spécifique :  
  
-   [GetBandCount](../Topic/CReBarCtrl::GetBandCount.md) récupère le nombre de bandes présentes dans le contrôle rebar.  
  
-   [GetBandInfo](../Topic/CReBarCtrl::GetBandInfo.md) initialise une structure de **REBARBANDINFO** avec les informations de la bande spécifiée.  Il existe une fonction membre correspondante pour [SetBandInfo](../Topic/CReBarCtrl::SetBandInfo.md).  
  
-   [GetRect](../Topic/CReBarCtrl::GetRect.md) récupère le rectangle englobant d'une bande spécifiée.  
  
-   [GetRowCount](../Topic/CReBarCtrl::GetRowCount.md) récupère le nombre de lignes de bande dans un contrôle rebar.  
  
-   [IDToIndex](../Topic/CReBarCtrl::IDToIndex.md) récupère l'index d'une bande spécifiée.  
  
-   [GetBandBorders](../Topic/CReBarCtrl::GetBandBorders.md) récupère les lignes d'une bande.  
  
 Outre la manipulation, plusieurs fonctions membres sont fournies qui vous permettent de traiter les bandes rebars spécifiques.  
  
 [InsertBand](../Topic/CReBarCtrl::InsertBand.md) et [DeleteBand](../Topic/CReBarCtrl::DeleteBand.md) ajoutent et suppriment des bandes rebars.  [MinimizeBand](../Topic/CReBarCtrl::MinimizeBand.md) et [MaximizeBand](../Topic/CReBarCtrl::MaximizeBand.md) affectent la taille actuelle d'une bande rebar spécifique.  [MoveBand](../Topic/CReBarCtrl::MoveBand.md) modifie l'index d'une bande rebar spécifique.  [ShowBand](../Topic/CReBarCtrl::ShowBand.md) affiche ou masque une bande rebar à l'utilisateur.  
  
 L'exemple suivant montre l'ajout d'une bande de la barre d'outils \(`m_wndToolBar`\) à un contrôle rebar existant \(`m_wndReBar`\).  La bande est décrite en initialisant la structure de `rbi` puis en appelant la fonction membre de `InsertBand` :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/CPP/rebar-controls-and-bands_1.cpp)]  
  
## Voir aussi  
 [Utilisation de CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)