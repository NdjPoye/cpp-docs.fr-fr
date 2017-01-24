---
title: "messages | Microsoft Docs"
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
  - "messages"
  - "messages, MFC"
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# messages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La boucle du message dans la fonction membre **Exécuter** de la classe `CWinApp` récupère les messages en file d'attente générés par différents événements.  Par exemple, lorsque l'utilisateur clique sur la souris, Windows envoie plusieurs messages liés à la souris, tels que `WM_LBUTTONDOWN` quand le bouton de la souris est cliqué et `WM_LBUTTONUP` quand le bouton de la souris est libéré.  L'implémentation de l'infrastructure de la boucle des messages d'application distribue le message dans la fenêtre appropriée.  
  
 Les catégories principales de messages sont décrites dans [Catégories de message](../mfc/message-categories.md).  
  
## Voir aussi  
 [Messages et commandes dans le Framework](../mfc/messages-and-commands-in-the-framework.md)