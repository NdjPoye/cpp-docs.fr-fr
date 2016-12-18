---
title: "M&#233;thode d&#39;appel de votre code par le Framework | Microsoft Docs"
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
  - "événements spécifiques à l'application (C++)"
  - "gestion des commandes, appeler les gestionnaires et le code dans MFC"
  - "routage des commandes, infrastructure"
  - "routage des commandes, MFC"
  - "flux de contrôle (C++), infrastructure MFC et votre code"
  - "événements (C++), routage des commandes dans MFC"
  - "événements (C++), programmation pilotée par événements"
  - "MFC (C++), appeler du code"
  - "MFC (C++), appeler du code (à partir de)"
ms.assetid: 39e68189-a580-40d0-9e35-bf5cd24a8ecf
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# M&#233;thode d&#39;appel de votre code par le Framework
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il est essentiel de comprendre la relation entre votre code source et le code dans l'infrastructure MFC.  Si votre application s'exécute, la plupart de l'ordre d'exécution se trouve dans le code de l'infrastructure.  L'infrastructure gère la boucle de message qui reçoit les messages Windows lorsque l'utilisateur sélectionne les commandes et modifie des données dans une vue.  Les événements que l'infrastructure peut gérer elle\-même ne reposent pas du tout sur votre code.  Par exemple, l'infrastructure sait comment fermer Windows et quitter l'application en réponse à des commandes de l'utilisateur.  Comme elle gère ces tâches, l'infrastructure utilise des gestionnaires de messages et des fonctions virtuelles C\+\+ pour vous donner des possibilités de répondre à ces événements.  Votre code ne se trouve pas dans la partie contrôle, toutefois ; l'infrastructure y est.  
  
 L'infrastructure appelle votre code pour les événements spécifiques à l'application.  Par exemple, lorsque l'utilisateur sélectionne une commande de menu, l'infrastructure dirige la commande dans une séquence d'objets C\+\+ : la vue actuelle et la fenêtre de cadre, le document associé à la vue, le modèle du document, et l'objet d'application.  Si un de ces objets peut gérer la commande, il le fait, en appelant la fonction gestionnaire des messages appropriée.  Pour toute commande, le code appelé peut être le votre ou celui de l'infrastructure.  
  
 Ce procédé est quelque peu familier aux programmeurs expérimentés de programmation traditionnelle pour Windows ou de programmation pilotée par les événements.  
  
 Dans les rubriques connexes, vous lirez ce que l'infrastructure fait quand elle démarre et exécute l'application puis nettoie lorsque l'application se termine.  Vous comprendrez également où s'intègre votre code.  
  
 Pour plus d'informations, consultez [Classe CWinApp : La classe d'application](../mfc/cwinapp-the-application-class.md) et [Modèles de document et processus de création de document\/vue](../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Voir aussi  
 [Génération à partir du Framework](../mfc/building-on-the-framework.md)