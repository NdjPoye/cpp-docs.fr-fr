---
title: "Info-bulles dans les fen&#234;tres non d&#233;riv&#233;es de CFrameWnd | Microsoft Docs"
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
  - "contrôles (MFC), info-bulles"
  - "activer les astuces"
  - "fonctions gestionnaires, info-bulles"
  - "Aide, astuces pour les contrôles"
  - "TOOLTIPTEXT (structure)"
  - "TTN_NEEDTEXT (message)"
ms.assetid: cad5ef0f-02e3-4151-ad0d-3d42e6932b0e
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Info-bulles dans les fen&#234;tres non d&#233;riv&#233;es de CFrameWnd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La famille d'article couvre l'activation des info\-bulles pour les contrôles contenus dans une fenêtre qui n'est pas dérivée de [CFrameWnd](../mfc/reference/cframewnd-class.md).  L'article [Info\-bulles des barres d'outils](../mfc/toolbar-tool-tips.md) fournit des informations sur les info\-bulles des contrôles dans `CFrameWnd`.  
  
 Les rubriques traitées dans cette famille d'articles sont les suivantes :  
  
-   [Activation des info\-bulles](../mfc/enabling-tool-tips.md)  
  
-   [Gestion de la notification TTN\_NEEDTEXT pour les info\-bulles](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)  
  
-   [La structure TOOLTIPTEXT](../mfc/tooltiptext-structure.md)  
  
 Les info\-bulles sont automatiquement affichées pour les boutons et d'autres contrôles contenus dans une fenêtre parente dérivée de `CFrameWnd`.  Cela est dû au fait que `CFrameWnd` possède un gestionnaire par défaut pour la notification [TTN\_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760269), qui traite les notifications **TTN\_NEEDTEXT** des contrôles d'info\-bulle associés aux contrôles.  
  
 Toutefois, ce gestionnaire par défaut n'est pas appelé lorsque la notification **TTN\_NEEDTEXT** est envoyée d'un contrôle d'info\-bulle associé à un contrôle dans une fenêtre qui n'est pas `CFrameWnd`, tel qu'un contrôle d'une boîte de dialogue ou une vue de formulaire.  Par conséquent, il est nécessaire que vous fournissiez une fonction gestionnaire du message de notification **TTN\_NEEDTEXT** pour afficher des info\-bulles des contrôles enfants.  
  
 Les info\-bulles données par défaut pour les fenêtres par [CWnd::EnableToolTips](../Topic/CWnd::EnableToolTips.md) n'ont pas de texte associé à celles\-ci.  Pour récupérer le texte afin que l'info\-bulle l'affiche, la notification **TTN\_NEEDTEXT** est envoyée à la fenêtre parente du contrôle d'info\-bulle juste avant que la fenêtre d'info\-bulle ne s'affiche.  S'il n'y a aucun gestionnaire pour ce message pour affecter une valeur au membre **pszText** de la structure **TOOLTIPTEXT**, il n'y a aucun texte affiché pour l'info\-bulle.  
  
## Voir aussi  
 [Info\-bulles](../mfc/tool-tips.md)