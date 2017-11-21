---
title: Gestion et mappage des messages | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 64a99bad7d6bc7fa937100cc5bf864e968572402
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="message-handling-and-mapping"></a>Gestion et mappage des messages
Cette série d’articles explique comment les messages et les commandes sont traitées par l’infrastructure MFC et comment les connecter à leurs fonctions gestionnaires.  
  
 Dans les programmes Windows traditionnels, les messages Windows sont gérées dans une instruction switch étendue dans une procédure de fenêtre. MFC utilise à la place [tables des messages](../mfc/message-categories.md) mapper les messages directs aux fonctions membres de classe distinct. Tables des messages sont plus efficaces que les fonctions virtuelles dans ce but, et ils permettent des messages d’être traités par l’objet C++ plus approprié : application, document, vue et ainsi de suite. Vous pouvez mapper un message unique ou une plage de messages, ID de commande, ou l’ID de contrôle.  
  
 **WM_COMMAND** messages — généralement générés par les menus, boutons de barre d’outils ou des accélérateurs, également utiliser le mécanisme de table des messages. MFC définit une norme [routage](../mfc/command-routing.md) de messages de commande entre l’application, frame fenêtre, de vue et de documents actifs dans votre programme. Vous pouvez remplacer ce routage si vous avez besoin.  
  
 Tables des messages également fournissent un moyen pour mettre à jour des objets d’interface utilisateur (par exemple, les menus et boutons de barre d’outils), l’activation ou la désactivation en fonction du contexte actuel.  
  
 Pour obtenir des informations générales sur les messages et les files d’attente de messages de Windows, consultez [Messages et les files d’attente](http://msdn.microsoft.com/library/windows/desktop/ms632590) dans le Kit de développement logiciel Windows.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Que voulez-vous en savoir plus  
  
-   [Messages et commandes dans le Framework](../mfc/messages-and-commands-in-the-framework.md)  
  
-   [Comment le framework appelle un gestionnaire de messages](../mfc/how-the-framework-calls-a-handler.md)  
  
-   [Comment le Framework effectue des recherches dans les tables des messages](../mfc/how-the-framework-searches-message-maps.md)  
  
-   [Déclaration des fonctions de gestionnaire de messages](../mfc/declaring-message-handler-functions.md)  
  
-   [Mappage des messages à des fonctions](../mfc/reference/mapping-messages-to-functions.md)  
  
-   [Comment afficher des informations sur les commandes dans la barre d’état](../mfc/how-to-display-command-information-in-the-status-bar.md)  
  
-   [Mise à jour dynamique des objets d’interface utilisateur](../mfc/how-to-update-user-interface-objects.md)  
  
-   [Guide pratique pour créer une table des messages pour une classe de modèle](../mfc/how-to-create-a-message-map-for-a-template-class.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Concepts](../mfc/mfc-concepts.md)   
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)   
 [CWnd (classe)](../mfc/reference/cwnd-class.md)   
 [CCmdTarget, classe](../mfc/reference/ccmdtarget-class.md)
