---
title: "Classes de routage des commandes | Microsoft Docs"
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
  - "vc.classes.command"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "routage des commandes, classes"
  - "MFC, routage des commandes"
ms.assetid: 4b50e689-2c54-4e6c-90f0-37333e22b2a1
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de routage des commandes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pendant que l'utilisateur interagit avec l'application en choisissant des menus ou des boutons de barre de contrôle avec la souris, l'application envoie un message de l'objet interface utilisateur affecté à un objet approprié de cible de la commande.  Les classes de cible de commande dérivées de `CCmdTarget` incluent [CWinApp](../mfc/reference/cwinapp-class.md), [CWnd](../mfc/reference/cwnd-class.md), [CDocTemplate](../mfc/reference/cdoctemplate-class.md), [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), et leurs classes dérivées.  L'infrastructure prend en charge le routage des commandes automatique afin que les commandes puissent être gérées par l'objet le plus approprié actuellement actifs dans l'application.  
  
 Un objet de la classe `CCmdUI` est transmis aux gestionnaires de l'interface utilisateur de mise à jour de votre cible de commande \([ON\_UPDATE\_COMMAND\_UI](../Topic/ON_UPDATE_COMMAND_UI.md)\) qui vous permettent de mettre à jour l'état de l'interface utilisateur pour une commande particulière \(par exemple, pour activer ou supprimer le contrôle des éléments de menu\).  Vous appelez les fonctions de membre de l'objet `CCmdUI` pour mettre à jour l'état de l'objet d'interface utilisateur.  Ce processus est le même que l'objet d'interface associé à une commande particulière est un élément de menu, un bouton ou les deux.  
  
 [CCmdTarget](../mfc/reference/ccmdtarget-class.md)  
 Sert de classe de base pour toutes les classes d'objets qui peuvent recevoir et répondre aux messages.  
  
 [CCmdUI](../mfc/reference/ccmdui-class.md)  
 Fournit une interface de programmation pour mettre à jour des objets interface utilisateur tels que les éléments de menu ou les boutons de la barre de contrôle.  L'objet cible de la commande active, désactive, vérifie, et\/ou libère l'objet d'interface utilisateur avec cet objet.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)