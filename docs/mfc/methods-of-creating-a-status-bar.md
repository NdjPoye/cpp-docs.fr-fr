---
title: "M&#233;thodes de cr&#233;ation d&#39;une barre d&#39;&#233;tat | Microsoft Docs"
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
  - "CStatusBar (classe), différences par rapport à CStatusBarCtrl"
  - "CStatusBarCtrl (classe), créer"
  - "CStatusBarCtrl (classe), différences par rapport à CStatusBar"
  - "méthodes (MFC)"
  - "méthodes (MFC), créer des barres d'état"
  - "barres d'état, créer"
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# M&#233;thodes de cr&#233;ation d&#39;une barre d&#39;&#233;tat
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC fournit deux classes pour créer des barres d'état : [CStatusBar](../mfc/reference/cstatusbar-class.md) et [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) \(qui encapsule l'API de contrôle commun Windows\).  `CStatusBar` fournit toutes les fonctionnalités du contrôle courant de barre d'état, elle interagit automatiquement avec les menus et les barres d'outils, et il gère plusieurs des paramètres et des structures nécessaire de contrôle commun pour vous ; toutefois, l'exécutable résultant est généralement supérieur à celui créé à l'aide de `CStatusBarCtrl`.  
  
 `CStatusBarCtrl` donne en général un plus petit fichier exécutable, préférez utiliser `CStatusBarCtrl` si vous n'envisagez pas d'intégrer la barre d'état dans l'architecture de MFC.  Si vous envisagez d'utiliser `CStatusBarCtrl` et pour intégrer la barre d'état dans l'architecture de MFC, vous devez prendre des précautions supplémentaires pour communiquer des manipulations de contrôle de la barre d'état à MFC.  Cette communication n'est pas difficile ; toutefois, il s'agit d'un travail supplémentaire qui n'est pas nécessaire lorsque vous utilisez `CStatusBar`.  
  
 Visual C\+\+ propose deux manières de tirer parti du contrôle courant de barre d'état.  
  
-   Créez la barre d'état à `CStatusBar`, puis appelez [CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md) pour obtenir l'accès aux fonctions membres de `CStatusBarCtrl`.  
  
-   Créez la barre d'état à l'aide du constructeur [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md).  
  
 L'une ou l'autre méthode vous donnera l'accès aux fonctions membres à partir de la barre d'état.  Lorsque vous appelez `CStatusBar::GetStatusBarCtrl`, il retourne une référence à un objet de `CStatusBarCtrl` donc vous pouvez utiliser l'un ou l'autre ensemble de fonctions de membre.  Voir le [CStatusBar](../mfc/reference/cstatusbar-class.md) pour plus d'informations sur la construction et créer une barre d'état à `CStatusBar`.  
  
## Voir aussi  
 [Utilisation de CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)