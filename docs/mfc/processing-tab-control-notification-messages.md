---
title: "Traitement des messages de notification du contr&#244;le Tab | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CTabCtrl (classe), notifications de traitement"
  - "notifications, traiter dans CTabCtrl"
  - "notifications, contrôles onglet"
  - "notifications de traitement"
  - "contrôles onglet, notifications de traitement"
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Traitement des messages de notification du contr&#244;le Tab
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque les utilisateurs cliquent sur des onglets ou boutons, le contrôle onglet \([CTabCtrl](../mfc/reference/ctabctrl-class.md)\) envoie des messages de notification dans la fenêtre parente.  Traitez ces messages si vous souhaitez effectuer quelque chose en réponse.  Par exemple, lorsque l'utilisateur clique sur un onglet, vous pouvez pré\-établir des paramètres dans la page avant de l'afficher.  
  
 Traitez les messages **WM\_NOTIFY** du contrôle d'onglet dans votre classe vue ou boîte de dialogue.  Utilisez la fenêtre Propriétés pour créer une fonction gestionnaire [OnChildNotify](../Topic/CWnd::OnChildNotify.md) avec une instruction SWITCH sur laquelle le message de notification est traité.  Pour obtenir la liste des notifications qu'un contrôle onglet peut envoyer à la fenêtre parente, consultez la section de **Notifications** [Référence de contrôle onglet](http://msdn.microsoft.com/library/windows/desktop/bb760548) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Voir aussi  
 [Utilisation de CTabCtrl](../mfc/using-ctabctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)