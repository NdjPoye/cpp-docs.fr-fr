---
title: "Comment les messages noncommand parviennent &#224; leurs gestionnaires | Microsoft Docs"
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
  - "gestion des messages (C++), noncommand (messages)"
  - "messages (C++), router"
  - "noncommand (messages)"
  - "messages Windows (C++), router"
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Comment les messages noncommand parviennent &#224; leurs gestionnaires
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Contrairement aux commandes, les messages standard windows ne sont pas routés via des cibles d'une ligne hiérarchique mais sont généralement gérés par la fenêtre à laquelle les fenêtres envoie le message.  La fenêtre peut être une fenêtre cadre principale, une fenêtre enfant MDI, un contrôle standard, une boîte de dialogue, une vue, ou un autre type de fenêtre enfant.  
  
 Au moment de l'exécution, chaque fenêtre de Windows est attachée à un objet dérivé \(directement ou indirectement d'`CWnd`\) qui possède une table des messages et gestionnaires fonctions associées.  L'infrastructure utilise la table des messages — comme dans une commande — pour mapper les messages entrants aux gestionnaires.  
  
## Voir aussi  
 [Méthode d'appel d'un gestionnaire par le Framework](../mfc/how-the-framework-calls-a-handler.md)