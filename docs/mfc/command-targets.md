---
title: "Cibles de la commande | Microsoft Docs"
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
  - "mappage des commandes"
  - "routage des commandes, cibles de la commande"
  - "cibles de la commande"
  - "messages, commande"
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cibles de la commande
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'illustration [Commandes dans l'infrastructure](../mfc/user-interface-objects-and-command-ids.md) indique la connexion entre un objet interface utilisateur, tel qu'un élément de menu, et la fonction gestionnaire qui appelle le framework pour exécuter la commande obtenue lorsque l'objet est sélectionné.  
  
 Windows envoie des messages qui ne sont pas des messages de commande directement dans une fenêtre dont le gestionnaire du message est ensuite appelé.  Toutefois, le framework route des commandes à plusieurs candidats objets  — appelés cibles de commande — l'un d'eux appelle normalement un responsable de la commande.  Les fonctions gestionnaires fonctionnent de la même manière pour les commandes et les messages standard Windows, mais les mécanismes par lesquels elles sont appelées sont différents, comme expliqué dans [Comment l'infrastructure appelle un gestionnaire](../mfc/how-the-framework-calls-a-handler.md).  
  
## Voir aussi  
 [Messages et commandes dans le Framework](../mfc/messages-and-commands-in-the-framework.md)