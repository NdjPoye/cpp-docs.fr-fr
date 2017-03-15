---
title: "Envoi et r&#233;ception de messages | Microsoft Docs"
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
  - "messages de notification de contrôle"
  - "messages (C++), MFC"
  - "messages (C++), recevoir"
  - "messages (C++), envoyer"
  - "MFC (C++), messages"
  - "messages Windows (C++), gérer dans MFC"
ms.assetid: 9ce189cb-b259-4c3b-b6f2-9cfbed18b98b
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Envoi et r&#233;ception de messages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Considérez la partie d'envoie du processus et comment l'infrastructure répond.  
  
 La plupart des messages résultent de l'interaction de l'utilisateur avec le programme.  Les commandes sont générées par les clics de la souris dans les éléments de menu ou des boutons de la barre d'outils ou par les séquences de touches d'accélérateur.  L'utilisateur génère également des messages Windows en redimensionnant ou déplaçant une fenêtre, par exemple.  D'autres messages Windows sont envoyés lorsque les événements tels que le démarrage du programme ou l'arrêt se produisent, comme les fenêtres d'obtention ou perdent le focus, et ainsi de suite.  Les messages de notification de contrôle sont générés par les clics de la souris ou d'autres interventions de l'utilisateur avec un contrôle, tel qu'un bouton ou un contrôle zone de liste déroulante de la boîte de dialogue.  
  
 La fonction membre du **Exécuter** de la classe `CWinApp` récupère les messages et les distribue dans la fenêtre appropriée.  La plupart des messages de commande sont transmis à la fenêtre principale de l'application.  Le `WindowProc` prédéfini par la bibliothèque de classes reçoit les messages et les itinéraires différemment, en fonction de la catégorie de message reçu.  
  
 Examinons à présent la partie réceptrice du processus.  
  
 Le récepteur initial d'un message doit être un objet fenêtre.  Les messages Windows sont généralement traités directement par l'objet fenêtre.  Les messages de commandes, provenant généralement de la fenêtre principale de l'application, deviennent routé à la chaîne de cible de la commande décrites dans [Routage des commandes](../mfc/command-routing.md).  
  
 Chaque objet en mesure de recevoir des messages ou des commandes possède sa propre table de messages ce qui lie un message ou une commande avec le nom de son responsable.  
  
 Lorsqu'un objet de la cible de la commande reçoit un message ou une commande, il trouve la table des messages pour une correspondance.  S'il détecte un gestionnaire du message, il appelle le gestionnaire.  Pour plus d'informations sur la façon dont les tables des messages sont détectées, consultez le [Comment l'infrastructure recherche des tables de messages](../mfc/how-the-framework-searches-message-maps.md).  Référez vous à nouveau à l'illustration [Commandes dans l'infrastructure](../mfc/user-interface-objects-and-command-ids.md).  
  
## Voir aussi  
 [Méthode d'appel d'un gestionnaire par le Framework](../mfc/how-the-framework-calls-a-handler.md)