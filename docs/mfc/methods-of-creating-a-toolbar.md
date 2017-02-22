---
title: "M&#233;thodes de cr&#233;ation d&#39;une barre d&#39;outils | Microsoft Docs"
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
  - "CToolBar (classe), créer des barres d'outils"
  - "CToolBarCtrl (classe), et classe CToolBar"
  - "CToolBarCtrl (classe), créer des barres d'outils"
  - "barres d'outils MFC"
  - "contrôles de barre d'outils (MFC)"
  - "contrôles de barre d'outils (MFC), créer"
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# M&#233;thodes de cr&#233;ation d&#39;une barre d&#39;outils
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC fournit deux classes pour créer des barres d'outils : [CToolBar](../mfc/reference/ctoolbar-class.md) et [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) \(qui encapsule l'API de contrôle commun Windows\).  `CToolBar` fournit toutes les fonctionnalités du contrôle commun de la barre d'outils, et il gère plusieurs des paramètres et des structures nécessaire de contrôle commun pour vous ; toutefois, l'exécutable résultant est généralement supérieur à celui créé à l'aide de `CToolBarCtrl`.  
  
 `CToolBarCtrl` est en général provoqué un plus petit fichier exécutable, et vous pouvez préférer pour utiliser `CToolBarCtrl` si vous n'envisagez pas d'intégrer la barre d'état dans l'architecture de MFC.  Si vous envisagez d'utiliser `CToolBarCtrl` et pour intégrer la barre d'état dans l'architecture de MFC, vous devez prendre des précautions supplémentaires pour communiquer des manipulations de contrôle de la barre d'état à MFC.  Cette communication n'est pas difficile ; toutefois, il s'agit d'un travail supplémentaire qui n'est pas nécessaire lorsque vous utilisez `CToolBar`.  
  
 Visual C\+\+ propose deux manières de tirer parti du contrôle courant de barre d'état.  
  
-   Créez la barre d'outils à `CToolBar`, puis appelez [CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md) pour obtenir l'accès aux fonctions membres d'`CToolBarCtrl`.  
  
-   Créez la barre d'outils à l'aide de le constructeur d'[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md).  
  
 L'une ou l'autre méthode vous donnera l'accès aux fonctions membres à partir de la barre d'état.  Lorsque vous appelez `CToolBar::GetToolBarCtrl`, il retourne une référence à un objet de `CToolBarCtrl` donc vous pouvez utiliser l'un ou l'autre ensemble de fonctions de membre.  Voir le [CToolBar](../mfc/reference/ctoolbar-class.md) pour plus d'informations sur la construction et créer une barre d'outils à `CToolBar`.  
  
## Voir aussi  
 [Utilisation de CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)