---
title: "Initialisation des parties d&#39;un objet CStatusBarCtrl | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
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
  - "CStatusBarCtrl (classe), déclarer des parties de"
  - "CStatusBarCtrl (classe), mode simple"
  - "icônes, utiliser dans les barres d'états"
  - "barres d'états simples"
  - "barres d'état, déclarer des parties de"
  - "barres d'état, icônes"
  - "barres d'état, mode simple"
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Initialisation des parties d&#39;un objet CStatusBarCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Par défaut, une barre d'état affiche les informations d'état à des volets distincts.  Ces volets \(également appelés éléments\) peuvent contenir une chaîne de texte, l'icône, ou les deux.  
  
 Utilisez [SetParts](../Topic/CStatusBarCtrl::SetParts.md) pour définir le nombre de parties, et la longueur, la barre d'état aura la valeur.  Après avoir créé les parties de la barre d'état, procédez aux appels à [SetText](../Topic/CStatusBarCtrl::SetText.md) et [SetIcon](../Topic/CStatusBarCtrl::SetIcon.md) pour définir le texte ou l'icône pour une partie spécifique de la barre d'état.  Une fois la partie a été correctement définie, le contrôle est automatiquement redessinée.  
  
 L'exemple suivant démarre un objet existant `CStatusBarCtrl` \(`m_StatusBarCtrl`\) avec quatre volets et affecte une icône \(IDI\_ICON1\) et un certain texte dans la deuxième partie.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/CPP/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]  
  
 Pour plus d'informations sur la définition du mode d'objet `CStatusBarCtrl` SIMPLE, consultez [Définir le mode d'objet de CStatusBarCtrl](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).  
  
## Voir aussi  
 [Utilisation de CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)