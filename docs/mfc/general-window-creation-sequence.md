---
title: "S&#233;quence de cr&#233;ation d&#39;une fen&#234;tre g&#233;n&#233;rale | Microsoft Docs"
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
  - "fenêtres frame (C++), créer"
  - "séquence (C++)"
  - "séquence (C++), création de fenêtres"
  - "fenêtres (C++), créer"
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
caps.latest.revision: 8
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# S&#233;quence de cr&#233;ation d&#39;une fen&#234;tre g&#233;n&#233;rale
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous créez une fenêtre de votre propre initiative, tel qu'une fenêtre fils, l'infrastructure utilise pratiquement le même processus que décrit dans [Création de documents\/vue](../mfc/document-view-creation.md).  
  
 Toutes les classes de fenêtres fournies par MFC utilisent [construction à deux niveaux](../mfc/one-stage-and-two-stage-construction-of-objects.md).  Autrement dit, pendant un appel de l'opérateur C\+\+ **new**, le constructeur alloue et initialise l'objet de l'actuel c \+\+ mais ne crée pas une fenêtre Windows correspondante.  Cela s'effectue après en appelant la fonction membre de [Créer](../Topic/CWnd::Create.md) de l'objet fenêtre.  
  
 La fonction membre du **Créer** de la fenêtre Windows et enregistre son `HWND` dans le membre de données public [m\_hWnd](../Topic/CWnd::m_hWnd.md)de l'objet C\+\+.  **Créer** offre une souplesse complète sur les paramètres de création.  Avant d'appeler **Créer**, vous pouvez stocker une classe de fenêtre avec la fonction globale [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) pour définir les styles d'icônes et de la classe pour le cadre.  
  
 Pour des fenêtres à cadre, vous pouvez utiliser la fonction membre de [LoadFrame](../Topic/CFrameWnd::LoadFrame.md) au lieu de **Créer**.  `LoadFrame` fait la fenêtre Windows utiliser moins de paramètres.  Il obtient de nombreuses valeurs par défaut des ressources, telles que la légende du cadre, l'icône, la table des accélérateurs, puis le menu.  
  
> [!NOTE]
>  L'icône, la table des accélérateurs, et le menu des ressources doivent avoir un ID de ressource commun, telles que **IDR\_MAINFRAME**, pour qu'ils soient chargés par LoadFrame.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Objets fenêtres](../mfc/window-objects.md)  
  
-   [Inscription de classes de fenêtre](../mfc/registering-window-classes.md)  
  
-   [Destruction d'objets fenêtres](../mfc/destroying-window-objects.md)  
  
-   [Création de fenêtres cadre de document](../mfc/creating-document-frame-windows.md)  
  
## Voir aussi  
 [Création de fenêtres](../mfc/creating-windows.md)