---
title: "Mappage des messages | Microsoft Docs"
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
  - "mappage des commandes"
  - "commandes, connecter à des fonctions de gestionnaires"
  - "commandes, mapper"
  - "mappages, commandes"
  - "mappages, messages"
  - "gestion des messages, connecter à des fonctions de gestionnaires"
  - "tables des messages, à propos des tables des messages"
  - "messages, mapper"
ms.assetid: 996f0652-0698-4b8c-b893-cdaa836d9d0f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Mappage des messages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chaque classe d'infrastructure qui peut recevoir des messages ou des commandes à sa propre « mappage de message. » L'infrastructure utilise le mappage de message pour connecter des messages et des commandes à leur fonctions responsables.  Toute classe dérivée de la classe `CCmdTarget` peut avoir une table des messages.  D'autres articles sur les tables des messages en détail et expliquent comment les utiliser.  
  
 Malgré le nom « mappage des messages; » les mappages de messages gèrent les messages et les commandes — les trois catégories de messages consignés dans [Catégories de message](../mfc/message-categories.md).  
  
## Voir aussi  
 [Messages et commandes dans le Framework](../mfc/messages-and-commands-in-the-framework.md)