---
title: "R&#233;ception des notifications de contr&#244;les communs | Microsoft Docs"
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
  - "ON_NOTIFY"
  - "WM_NOTIFY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles communs (C++), notifications"
  - "contrôles (MFC), notifications"
  - "notifications, contrôles communs"
  - "ON_NOTIFY (macro)"
  - "OnNotify (méthode)"
  - "recevoir des notifications de contrôles communs"
  - "contrôles Windows communs (C++), notifications"
  - "WM_NOTIFY (message)"
ms.assetid: 50194592-d60d-44d0-8ab3-338a2a2c63e7
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# R&#233;ception des notifications de contr&#244;les communs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les contrôles communs sont des fenêtres enfants qui envoient des messages de notification de la fenêtre parente lorsque des événements, tels que des entrées utilisateur, se produisent dans le contrôle.  
  
 L'application s'appuie sur ces messages de notification pour déterminer quelle action l'utilisateur souhaite qu'elle effectue.  La plupart des contrôles communs envoient des messages de notification comme des messages **WM\_NOTIFY**.  Les contrôles Windows envoie la plupart des messages de notification comme des messages **WM\_COMMAND**.  [CWnd::OnNotify](../Topic/CWnd::OnNotify.md) est le responsable du message **WM\_NOTIFY**.  Comme avec `CWnd::OnCommand`, l'implémentation de `OnNotify` distribue le message de notification à `OnCmdMsg` pour gérer des tables des messages.  L'entrée de la table des messages de gestion des notifications est `ON_NOTIFY`.  Pour plus d'informations, consultez la [Note technique 61 : Messages ON\_NOTIFY et WM\_NOTIFY](../mfc/tn061-on-notify-and-wm-notify-messages.md).  
  
 Sinon, une classe dérivée peut traiter ses propres messages de notification avec "renvoi du message". Pour plus d'informations, consultez la [Note technique 62 : Renvoi de message pour les contrôles Windows](../mfc/tn062-message-reflection-for-windows-controls.md).  
  
## Récupérer la position du curseur dans un message de notification  
 Occasionnellement, il est utile de déterminer la position actuelle du curseur lorsque certains messages de notification sont reçus par un contrôle commun.  Par exemple, il est utile de déterminer l'emplacement du curseur actuel lorsqu'un contrôle commun reçoit un message de notification **NM\_RCLICK**.  
  
 Il existe un moyen simple d'y parvenir en appelant `CWnd::GetCurrentMessage`.  Toutefois, cette méthode extrait uniquement la position du curseur lorsque le message a été envoyé.  Étant donné que le curseur a peut\-être été supprimé depuis que le message a été envoyé vous devez appeler **CWnd::GetCursorPos** pour obtenir la position actuelle du curseur.  
  
> [!NOTE]
>  `CWnd::GetCurrentMessage` doit être appelé uniquement dans un gestionnaire de messages.  
  
 Ajoutez le code dans le corps du gestionnaire de messages de notification \(dans cet exemple, **NM\_RCLICK**\) :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/CPP/receiving-notification-from-common-controls_1.cpp)]  
  
 À ce stade, l'emplacement du curseur de la souris est stocké dans l'objet `cursorPos`.  
  
## Voir aussi  
 [Création et utilisation de contrôles](../mfc/making-and-using-controls.md)   
 [Contrôles](../mfc/controls-mfc.md)