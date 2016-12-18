---
title: "Cat&#233;gories de messages | Microsoft Docs"
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
  - "messages de commande (C++)"
  - "messages de notification de contrôle"
  - "contrôles (MFC), notifications"
  - "gestion des messages (C++), types de message"
  - "messages (C++), catégories"
  - "messages (C++), Windows"
  - "messages Windows (C++), catégories"
ms.assetid: 68e1db75-9da6-4a4d-b2c2-dc4d59f8d87b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cat&#233;gories de messages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour les types de messages écrivez\-vous des gestionnaires ?  Il existe trois catégories :  
  
1.  messages Windows  
  
     Il s'agit essentiellement ces messages commençant par le préfixe de **WM\_**, à l'exception **WM\_COMMAND**.  Les messages windows sont traités par windows et les vues.  Ces messages peuvent occuper des paramètres qui sont utilisés pour déterminer comment traiter le message.  
  
2.  notification de contrôle  
  
     Cela inclut des messages de notification de **WM\_COMMAND** les contrôles et d'autres fenêtres enfants vers les fenêtres parent.  Par exemple, un contrôle d'édition de qui est un message de **WM\_COMMAND** contenant le code de contrôle notification **EN\_CHANGE** lorsque l'utilisateur a pris une mesure qui peut avoir modifié le texte du contrôle d'édition.  Le gestionnaire de la fenêtre du message répond au message de notification d'une certaine façon appropriée, comme récupérer le texte du contrôle.  
  
     L'infrastructure achemine les messages de notification contrôle comme les autres messages de **WM\_**.  Une exception ; toutefois, est le message de notification de contrôle **BN\_CLICKED** envoyé par les boutons lorsque l'utilisateur clique sur les.  Ce message est traité en particulier en tant que message de commande et routé comme les autres commandes.  
  
3.  messages de commande  
  
     Cela inclut des messages de notification de **WM\_COMMAND** des objets d'interface utilisateur : menus, les boutons de la barre d'outils, et touches accélérateur.  L'infrastructure traite des commandes différemment des autres messages, et elles peuvent être gérées par des types d'objets, comme expliqué dans [Cible de la commande](../mfc/command-targets.md).  
  
##  <a name="_core_windows_messages_and_control.2d.notification_messages"></a> Messages windows et les messages de notification contrôle  
 Les messages dans les catégories 1 et 2 — les messages windows et les notifications de contrôle \)sont traités par windows : objets de classes dérivées de la classe `CWnd`.  Cela inclut `CFrameWnd`, `CMDIFrameWnd`, `CMDIChildWnd`, `CView`, `CDialog`, et vos propres classes dérivées des classes de base.  De tels objets encapsulent `HWND`, un descripteur de la fenêtre du windows.  
  
##  <a name="_core_command_messages"></a> OCM\_COMMAND \(message\)  
 Les messages dans la catégorie 3 — les commandes et peuvent être traités par les objets larges de divers : documents, des modèles de document, et l'objet d'application lui\-même en plus de les fenêtres et les vues.  Lorsqu'une commande affecte directement un certain objet particulier, il est logique d'avoir ce handle d'objet de la commande.  Par exemple, la commande ouverte dans le menu Fichier est logiquement associée à l'application : l'application ouvre un document spécifié en acceptant la commande.  Et le gestionnaire de la commande ouverte est une fonction membre de la classe d'application.  Pour plus d'informations sur les commandes et leur mode routés aux objets, consultez l'[Comment l'infrastructure appelle un gestionnaire](../mfc/how-the-framework-calls-a-handler.md).  
  
## Voir aussi  
 [Messages et commandes dans le Framework](../mfc/messages-and-commands-in-the-framework.md)