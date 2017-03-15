---
title: "Utilisation d&#39;info-bulles dans un objet CStatusBarCtrl | Microsoft Docs"
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
  - "CStatusBarCtrl (classe), info-bulles"
  - "barres d'état, info-bulles"
  - "info-bulles (C++), utiliser dans les barres d'états"
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Utilisation d&#39;info-bulles dans un objet CStatusBarCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour activer les info\-bulles pour un contrôle de barre d'état, créez l'objet `CStatusBarCtrl` avec le style **SBT\_TOOLTIPS**.  
  
> [!NOTE]
>  Si vous utilisez un objet `CStatusBar` pour implémenter la barre d'état, utilisez la fonction `CStatusBar::CreateEx`.  Elle vous permet de spécifier des styles supplémentaires pour l'objet incorporé **CStatusBarCtrl** .  
  
 Une fois que l'objet `CStatusBarCtrl` a été créé, utilisez [CStatusBarCtrl::SetTipText](../Topic/CStatusBarCtrl::SetTipText.md) et [CStatusBarCtrl::GetTipText](../Topic/CStatusBarCtrl::GetTipText.md) pour définir et récupérer le texte d'indication pour un volet spécifique.  
  
 Une fois que l'info\-bulle a été définie, elle s'affiche uniquement si la partie possède une icône et aucun texte, ou si tout le texte ne peut pas être restitué dans la partie.  Les info\-bulles ne sont pas prises en charge en mode simple.  
  
## Voir aussi  
 [Utilisation de CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)