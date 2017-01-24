---
title: "OnCmdMsg, gestionnaire | Microsoft Docs"
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
  - "OnCmdMsg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "routage des commandes, OnCmdMsg (gestionnaire)"
  - "gestionnaires"
  - "gestionnaires, OnCmdMessage"
  - "messages, router"
  - "OnCmdMessage (méthode)"
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OnCmdMsg, gestionnaire
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

To accomplish the routing of commands, each command target calls the `OnCmdMsg` member function of the next command target in the sequence.  Command targets use `OnCmdMsg` to determine whether they can handle a command and to route it to another command target if they cannot handle it.  
  
 Each command\-target class may override the `OnCmdMsg` member function.  The overrides let each class route commands to a particular next target.  A frame window, for example, always routes commands to its current child window or view, as shown in the table [Standard Command Route](../mfc/command-routing.md).  
  
 The default `CCmdTarget` implementation of `OnCmdMsg` uses the message map of the command\-target class to search for a handler function for each command message it receives — in the same way that standard messages are searched.  If it finds a match, it calls the handler.  Message\-map searching is explained in [How the Framework Searches Message Maps](../mfc/how-the-framework-searches-message-maps.md).  
  
## Voir aussi  
 [Méthode d'appel d'un gestionnaire par le Framework](../mfc/how-the-framework-calls-a-handler.md)