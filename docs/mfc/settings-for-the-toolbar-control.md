---
title: "Param&#232;tres du contr&#244;le ToolBar | Microsoft Docs"
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
  - "CToolBarCtrl (classe), paramètres"
  - "contrôles de barre d'outils (MFC), à propos des contrôles de barre d'outils"
ms.assetid: 025ba920-b3ee-4d82-9367-e652cd7875b9
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Param&#232;tres du contr&#244;le ToolBar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les boutons de la barre d'outils peuvent afficher une image, une chaîne, ou les deux.  Par défaut, la taille de l'image est définie aux dimensions de 16 par 15 pixels.  Tous les boutons sont de la même largeur, par défaut 24 par 22 pixels.  La hauteur d'une barre d'outils est déterminée par la hauteur des boutons, et la largeur de la barre d'outils est identique à la largeur de la zone client parente de la fenêtre, également par défaut.  
  
 Une barre d'outils qui peut avoir des fonctionnalités intégrées de personnalisation, notamment la boîte de dialogue définie par le système de personnalisation, qui permettent à l'utilisateur d'insérer, de supprimer, ou de réorganiser les boutons de la barre d'outils.  Une application détermine si les fonctionnalités de personnalisation sont disponibles pour l'utilisateur et contrôle le point à partir duquel l'utilisateur peut personnaliser la barre d'outils.  Pour plus d'informations sur la personnalisation la barre d'outils, consultez la classe [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) dans *le guide de MFC*.  
  
## Voir aussi  
 [Utilisation de CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)