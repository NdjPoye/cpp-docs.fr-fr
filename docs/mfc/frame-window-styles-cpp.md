---
title: "Styles de fen&#234;tre frame (C++) | Microsoft Docs"
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
  - "fenêtres frame (C++), styles"
  - "MFC (C++), fenêtres frame"
  - "PreCreateWindow (méthode), définir des styles de fenêtres"
  - "styles, fenêtres"
  - "styles de fenêtres (C++)"
  - "fenêtres (C++), MFC"
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
caps.latest.revision: 8
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Styles de fen&#234;tre frame (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fenêtres cadres que vous obtenez avec le framework conviennent pour la plupart des programmes, mais vous pouvez bénéficier d'une souplesse supplémentaire à l'aide des fonctions avancées [PreCreateWindow](../Topic/CWnd::PreCreateWindow.md) et de la fonction globale [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) de MFC.  `PreCreateWindow` est une fonction membre de `CWnd`.  
  
 Si vous appliquez des styles **WS\_HSCROLL** et **WS\_VSCROLL** à la fenêtre cadre principale, ils sont plutôt appliqués à la fenêtre de **MDICLIENT** afin que les utilisateurs puissent faire défiler la zone **MDICLIENT**.  
  
 Si le bit de style **FWS\_ADDTOTITLE** de la fenêtre est défini \(ce qu'il est par défaut\), la vue affiche dans la fenêtre cadre le titre à afficher dans la barre de titre de la fenêtre selon le nom de la vue du document.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Gestion des fenêtres enfants MDI \(MDICLIENT\)](../mfc/managing-mdi-child-windows.md), la fenêtre dans un cadre MDI qui contient les fenêtres enfants MDI  
  
-   [Modification des styles d'une fenêtre créée par MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
-   [Styles de fenêtre](../mfc/reference/window-styles.md)  
  
## Voir aussi  
 [Fenêtres frame](../mfc/frame-windows.md)