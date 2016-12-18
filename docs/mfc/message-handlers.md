---
title: "Gestionnaires de messages | Microsoft Docs"
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
  - "gestion des commandes, gestionnaires de messages"
  - "gestionnaires"
  - "gestionnaires, commande"
  - "gestionnaires, message"
  - "gestionnaires de messages"
  - "gestion des messages, gestionnaire de messages (fonctions)"
ms.assetid: 51bc4e76-dbe3-4cc2-b026-3199d56b2fa9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestionnaires de messages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans MFC, une *fonction gestionnaire* dédiée traite chaque message indépendant.  Les fonctions gestionnaires de messages sont des méthodes d'une classe.  Cette documentation utilise les termes *méthode gestionnaire de messages*, *fonction gestionnaire des messages*, *gestionnaire de messages*, et *gestionnaire* de façon interchangeable.  Certains types de gestionnaires de messages sont également appelés « gestionnaires de commandes. »  
  
 Écrire des gestionnaires de messages représente une grande proportion de votre travail dans l'écrit d'une application framework.  La famille d'article explique comment le mécanisme de traitement des messages s'exécute.  
  
 Que fait le gestionnaire d'un message ?  Il effectue ce que vous souhaitez fait en réponse à ce message.  Vous pouvez créer des gestionnaires à l'aide de la fenêtre Propriétés de la classe, puis exécutez le code du gestionnaire à l'aide de l'éditeur de code source.  
  
 Vous pouvez utiliser les fonctionnalités de Microsoft Visual C\+\+ et de MFC pour écrire les gestionnaires.  Pour obtenir la liste de toutes les classes, consultez [Présentation de la bibliothèque de classes](../mfc/class-library-overview.md) dans *le guide de MFC*.  
  
## Voir aussi  
 [Messages et commandes dans le Framework](../mfc/messages-and-commands-in-the-framework.md)