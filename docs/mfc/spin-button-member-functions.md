---
title: "Bouton toupie, fonctions membres | Microsoft Docs"
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
  - "CSpinButtonCtrl (classe), méthodes"
  - "contrôle toupie, méthodes"
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Bouton toupie, fonctions membres
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il existe plusieurs fonctions membres disponibles pour le contrôle de rotation \([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)\).  Utilisez ces fonctions pour modifier les attributs suivants de la toupie.  
  
-   **Acceleration** Ajustez la fréquence à laquelle la position change lorsque l'utilisateur maintient le bouton fléché.  Pour utiliser l'accélération, utilisez les fonctions membres de [EnsembleAccelerations](../Topic/CSpinButtonCtrl::SetAccel.md) et de [ObtenirAcceleration](../Topic/CSpinButtonCtrl::GetAccel.md).  
  
-   **Base** Modifiez la base \(10 ou 16\) utilisée pour afficher la position de la légende de la fenêtre associé.  Pour utiliser la base, utilisez les fonctions membres de [ObtenirBase](../Topic/CSpinButtonCtrl::GetBase.md) et de [EnsembleBase](../Topic/CSpinButtonCtrl::SetBase.md).  
  
-   **Buddy Window** Définissez dynamiquement la fenêtre associée.  Pour interroger ou modifier le fait que le contrôle est la fenêtre associé, utilisez les fonctions membres de [GetBuddy](../Topic/CSpinButtonCtrl::GetBuddy.md) et de [SetBuddy](../Topic/CSpinButtonCtrl::SetBuddy.md).  
  
-   **Position** Interrogez et modifiez la position.  Pour utiliser directement la position, utilisez les fonctions membres de [ObtenirPosition](../Topic/CSpinButtonCtrl::GetPos.md) et de [EnsemblePositions](../Topic/CSpinButtonCtrl::SetPos.md).  Étant donné que la légende du contrôle associé peut avoir changé \(par exemple, dans le cas de les états\-unis\) est un contrôle d'édition\), `GetPos` récupère la légende actuelle et ajuste la position en conséquence.  
  
-   **Plage** Modifier les positions de la valeur maximale et minimale pour le bouton de spin.  Par défaut, la valeur maximale est 0, et la valeur minimale de est 100.  Étant donné que la valeur maximale par défaut est inférieure à la valeur minimale par défaut, les actions des boutons fléchés est compteur\- intuitif.  Généralement, vous définissez la plage à l'aide de la fonction membre de [EnsemblePlage](../Topic/CSpinButtonCtrl::SetRange.md).  Pour interroger l'utilisation [ObtenirPlage](../Topic/CSpinButtonCtrl::GetRange.md)de plage.  
  
## Voir aussi  
 [Utilisation de CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)