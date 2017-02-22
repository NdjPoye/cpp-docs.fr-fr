---
title: "Utilisation de CStatusBarCtrl pour cr&#233;er un objet CStatusBarCtrl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl (classe), créer"
  - "contrôles de barre d'état, créer"
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Utilisation de CStatusBarCtrl pour cr&#233;er un objet CStatusBarCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Voici un exemple d'utilisation typique de [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md):  
  
### Utiliser un contrôle de barre d'état avec des parties  
  
1.  Construisez l'objet `CStatusBarCtrl`.  
  
2.  Appelez [SetMinHeight](../Topic/CStatusBarCtrl::SetMinHeight.md) si vous souhaitez définir la hauteur minimale de la zone de dessin du contrôle de barre d'état.  
  
3.  Appelez [SetBkColor](../Topic/CStatusBarCtrl::SetBkColor.md) pour définir la couleur d'arrière\-plan du contrôle de barre d'état.  
  
4.  Appelez [SetParts](../Topic/CStatusBarCtrl::SetParts.md) pour définir le nombre de parties dans un contrôle de barre d'état et la coordonnée du bord droit de chaque partie.  
  
5.  Appelez [SetText](../Topic/CStatusBarCtrl::SetText.md) pour définir le texte dans une partie de la barre d'état.  Le message invalide la partie du contrôle qui a changé, ce qui vous permet d'afficher le nouveau texte lorsque le contrôle reçoit ensuite le message `WM_PAINT`.  
  
 Dans certains cas, la barre d'état n'a besoin que d'afficher une ligne de texte.  Dans ce cas, effectuez un appel à [SetSimple](../Topic/CStatusBarCtrl::SetSimple.md).  Cela met le contrôle de la barre d'état dans le mode "simple", qui affiche une seule ligne de texte.  
  
## Voir aussi  
 [Utilisation de CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)