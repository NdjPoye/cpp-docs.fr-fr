---
title: "O&#249; trouver des tables de messages | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rechercher des tables des messages"
  - "macros, table des messages"
  - "tables des messages, rechercher"
  - "table des messages (macros)"
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# O&#249; trouver des tables de messages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous créez une application squelette avec l'Assistant d'Application, l'Assistant d'Application enregistre une table de messages pour chaque classe de commande de cible qu'elle crée pour vous.  Cela inclut vos application dérivée, document, vue, et les classes cadre de fenêtre.  Certaines de ces tables des messages ont déjà les entrées fournies par l'Assistant d'Application pour certains messages et commandes prédéfinies, et d'autres sont simplement des espaces réservés pour les gestionnaires que vous ajouterez.  
  
 La table des messages d'une classe se trouve dans le fichier .cpp de la classe.  En travaillant avec les tables des messages de base que l'Assistant d'Application crée, vous utilisez la fenêtre Propriétés pour ajouter des entrées pour les messages et commandes que chaque classe gèrera.  Une table classique des messages peut ressembler à ce qui suit après avoir ajouté des entrées :  
  
 [!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/CPP/where-to-find-message-maps_1.cpp)]  
  
 La table des messages se compose d'une collection de macros.  Deux macros, [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md) et [END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md), encadrent la table des messages.  Les macros, telles que `ON_COMMAND`, complètent le contenu de la table des messages.  
  
> [!NOTE]
>  Les macros table des messages ne sont pas suivies par des points\-virgules.  
  
 Lorsque vous utilisez l'assistant d'Ajout de la Classe pour créer une classe, il fournit une table des messages de la classe.  Ou bien, vous pouvez créer une table de messages manuellement à l'aide de l'éditeur de code source.  
  
## Voir aussi  
 [Comment le Framework effectue des recherches dans les tables des messages](../mfc/how-the-framework-searches-message-maps.md)