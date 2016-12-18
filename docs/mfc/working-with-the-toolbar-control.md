---
title: "Utilisation du contr&#244;le ToolBar | Microsoft Docs"
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
  - "CToolBarCtrl (classe), accéder à la barre d'outils"
  - "GetToolBarCtrl (méthode)"
  - "contrôles de barre d'outils (MFC), accéder"
  - "barres d'outils (C++), accéder au contrôle commun"
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation du contr&#244;le ToolBar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment vous pouvez accéder à l'objet [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sous\-jacentes à une [CToolBar](../mfc/reference/ctoolbar-class.md) pour un contrôle optimisé de barres d'outils.  Ceci est une rubrique avancée.  
  
## Procédures  
  
#### Pour accéder au contrôle commun de la barre d'outils sous\-jacentes à l'objet CToolBar  
  
1.  Appelez [CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md).  
  
 `GetToolBarCtrl` retourne une référence à un objet [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md).  Vous pouvez utiliser la référence aux fonctions membres d'appel de la classe de contrôle de la barre d'outils.  
  
> [!CAUTION]
>  Lors de l'appel des fonctions `CToolBarCtrl`**Obtenir** est sécurisé, soyez prudent si vous appelez les fonctions**Set**.  Ceci est une rubrique avancée.  Normalement vous n'avez pas à accéder au contrôle de la barre d'outils sous\-jacent.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Contrôles \(contrôles communs de Windows\)](../mfc/controls-mfc.md)  
  
-   [Notions de base de barre d'outils](../mfc/toolbar-fundamentals.md)  
  
-   [Ancrer et rendre flottantes les barres d'outils](../mfc/docking-and-floating-toolbars.md)  
  
-   [Redimensionner dynamiquement la barre d'outils](../mfc/docking-and-floating-toolbars.md)  
  
-   [Info\-bulles de barre d'outils](../mfc/toolbar-tool-tips.md)  
  
-   [Le survol des mises à jour des barres de statuts.](../mfc/toolbar-tool-tips.md)  
  
-   [Gestion des notifications pour les info\-bulles](../mfc/handling-tool-tip-notifications.md)  
  
-   Les classes [CToolBar](../mfc/reference/ctoolbar-class.md) et [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
  
-   [Gestion des notifications de personnalisation](../mfc/handling-customization-notifications.md)  
  
-   [Plusieurs barres d'outils](../mfc/toolbar-fundamentals.md)  
  
-   [Utilisation de vos anciennes barres d'outils](../mfc/using-your-old-toolbars.md)  
  
-   [Barres de contrôles](../mfc/control-bars.md)  
  
 Pour obtenir des informations générales sur l'utilisation des contrôles communs Windows, consultez [Contrôles communs](http://msdn.microsoft.com/library/windows/desktop/bb775493).  
  
## Voir aussi  
 [Implémentation de la barre d'outils MFC](../mfc/mfc-toolbar-implementation.md)