---
title: "Activation des info-bulles | Microsoft Docs"
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
  - "activer les astuces"
  - "initialiser les astuces"
  - "info-bulles (C++), activer"
  - "info-bulles (C++), initialiser"
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Activation des info-bulles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Activez la prise en charge des info\-bulles pour les contrôles enfants d'une fenêtre \(tels que les contrôles sur un formulaire ou une boîte de dialogue\).  
  
### Pour activer les info\-bulles des contrôles enfants d'une fenêtre  
  
1.  Appelez `EnableToolTips` pour la fenêtre pour laquelle vous souhaitez fournir des info\-bulles.  
  
2.  Spécifiez une chaîne pour chaque contrôle dans le gestionnaire de [Notifications de TTN\_NEEDTEXT](../mfc/handling-ttn-needtext-notification-for-tool-tips.md).  Le gestionnaire est dans la table des messages de la fenêtre qui contient les contrôles enfants \(par exemple, votre classe en mode formulaire\).  Ce gestionnaire doit appeler une fonction qui identifie le contrôle et définit **pszText** pour spécifier le texte utilisé par le contrôle d'une info\-bulle.  
  
## Voir aussi  
 [Info\-bulles dans les fenêtres non dérivées de CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)