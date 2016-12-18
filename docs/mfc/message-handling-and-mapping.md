---
title: "Gestion et mappage des messages | Microsoft Docs"
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
  - "gestion des messages"
  - "tables des messages"
  - "MFC, messages"
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestion et mappage des messages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La famille d'articles décrit comment les messages et les commandes sont traités par l'interface MFC et comment les connecter à leurs fonctions de gestion.  
  
 Dans les programmes traditionnels pour windows, les messages windows sont traités dans une grande instruction SWITCH dans une procédure d'affichage.  MFC utilise plutôt [des tables des messages](../mfc/message-categories.md) pour mapper les messages directs aux fonctions distinctes des membres de la classe.  Les tables des messages sont plus efficaces que les fonctions virtuelles à cet effet, et ils acceptent des messages à gérer par le plus appropriée objet application C\+\+, document, render, et ainsi de suite.  Vous pouvez mapper un seul message ou une plage de messages, réordonner les ID, ou des ID de contrôle.  
  
 Les messages de**WM\_COMMAND** — généralement générés par les menus, les boutons de la barre d'outils, ou des accélérateurs et utilisez également le mécanisme de table des messages.  MFC définit un niveau [routage](../mfc/command-routing.md) les messages de commande entre l'application, la fenêtre frame, la vue, et les documents actifs dans votre programme.  Vous pouvez remplacer le routage si vous avez besoin.  
  
 Les tables des messages fournissent également une méthode pour mettre à jour des objets interface utilisateur \(par exemple les menus et les boutons de la barre d'outils\), l'activation ou la désactivation en fonction de le contexte actuel.  
  
 Pour obtenir des informations générales sur les messages et les files d'attente de messages dans windows, consultez [Messages et les Files d'attente de messages](http://msdn.microsoft.com/library/windows/desktop/ms632590) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Messages et commandes dans le Framework](../mfc/messages-and-commands-in-the-framework.md)  
  
-   [Comment l'interface appelle le gestionnaire de messages](../mfc/how-the-framework-calls-a-handler.md)  
  
-   [Comment le Framework effectue des recherches dans les tables des messages](../mfc/how-the-framework-searches-message-maps.md)  
  
-   [Déclaration des fonctions de gestionnaire de messages](../mfc/declaring-message-handler-functions.md)  
  
-   [Mappage de messages à des fonctions](../mfc/reference/mapping-messages-to-functions.md)  
  
-   [Comment afficher les informations sur les commandes dans la barre d'état](../mfc/how-to-display-command-information-in-the-status-bar.md)  
  
-   [Mise à jour dynamique des objets interface utilisateur](../mfc/how-to-update-user-interface-objects.md)  
  
-   [Comment : créer une table des messages pour une classe de modèle](../mfc/how-to-create-a-message-map-for-a-template-class.md)  
  
## Voir aussi  
 [Concepts](../mfc/mfc-concepts.md)   
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)   
 [CWnd, classe](../mfc/reference/cwnd-class.md)   
 [CCmdTarget Class](../mfc/reference/ccmdtarget-class.md)