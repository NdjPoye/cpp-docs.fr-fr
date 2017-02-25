---
title: "OnIdle, fonction membre | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OnIdle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinApp (classe), OnIdle (méthode)"
  - "traitement des boucles inactives"
  - "gestion des messages, OnIdle (méthode)"
  - "OnIdle (méthode)"
  - "traiter des messages"
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OnIdle, fonction membre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'aucun message Windows n'est traité, l'infrastructure appelle la méthode [CWinApp](../mfc/reference/cwinapp-class.md)[OnIdle](../Topic/CWinApp::OnIdle.md) \(décrite dans la référence de la bibliothèque MFC\).  
  
 Substitue `OnIdle` pour effectuer des tâches en arrière\-plan.  La version par défaut met à jour l'état des objets interface utilisateur tels que les boutons de la barre d'outils et effectue le nettoyage des objets temporaires créés par l'infrastructure dans le cadre de ses opérations.  L'illustration suivante montre comment la boucle de message appelle `OnIdle` lorsqu'il n'existe aucun message dans la file d'attente.  
  
 ![Processus de boucle de message](../mfc/media/vc387c1.png "vc387C1")  
La boucle de message  
  
 Pour plus d'informations sur les opérations réalisables dans la boucle d'inactivité, consultez [Traitement des boucles d'inactivité](../mfc/idle-loop-processing.md).  
  
## Voir aussi  
 [CWinApp : classe d'application](../mfc/cwinapp-the-application-class.md)