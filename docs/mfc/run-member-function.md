---
title: "Ex&#233;cuter une fonction membre | Microsoft Docs"
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
  - "CWinApp (classe), Run"
  - "pompe de messages dans CWinApp::Run"
  - "messages, boucles"
  - "Run (méthode), messages et traitement des temps d'inactivité"
  - "WinMain (méthode)"
  - "WinMain (méthode), appels (CWinApp::Run)"
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ex&#233;cuter une fonction membre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une application d'infrastructure passe la majeure partie de son temps dans la fonction membre d' [Exécuter](../Topic/CWinApp::Run.md) de la classe [CWinApp](../mfc/reference/cwinapp-class.md).  Après l'initialisation, `WinMain` appelle **Exécuter** pour traiter la boucle du message.  
  
 **Exécuter** parcourt via une boucle de message, en vérifiant la file d'attente de messages pour les messages disponibles.  Si un message est disponible, **Exécuter** le répartit pour l'action.  Si aucun message n'est disponible, ce qui arrive souvent, **Exécuter** appelle `OnIdle` pour effectuer n'importe quel traitement des temps d'inactivité que vous ou l'infrastructure pouvez nécessiter d'être fait.  En l'absence de tout message et de tout traitement des temps d'inactivité à faire, l'application attend que quelque chose se produise.  Lorsque l'application se termine, **Exécuter** appelle `ExitInstance`.  La figure dans [Fonction membre d'OnIdle](../mfc/onidle-member-function.md) montre la séquence d'actions de la boucle du message.  
  
 La distribution de messages dépend du type de message.  Pour plus d'informations, consultez [Messages et commandes dans l'infrastructure](../mfc/messages-and-commands-in-the-framework.md).  
  
## Voir aussi  
 [CWinApp : classe d'application](../mfc/cwinapp-the-application-class.md)