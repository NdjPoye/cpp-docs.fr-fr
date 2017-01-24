---
title: "Message Maps (ATL) | Microsoft Docs"
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
  - "ATL, gestionnaires de messages"
  - "message maps, ATL"
ms.assetid: 9e100400-65c7-4a85-8857-4e6cb6dd7340
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Message Maps (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une table des messages associe une fonction gestionnaire avec un message particulier, une commande, ou une notification.  À l'aide de [macros de table des messages](../atl/reference/message-map-macros-atl.md)ATL, vous pouvez spécifier une table des messages pour une fenêtre.  Les procédures de fenêtre dans `CWindowImpl`, `CDialogImpl`, et `CContainedWindowT` dirigent les messages d'une fenêtre à sa table des messages.  
  
 [fonctions gestionnaires de messages](../atl/message-handler-functions.md) acceptent un argument de type `BOOL&`.  Cet argument indique si un message a été traité, et il est défini à `TRUE` par défaut.  Une fonction gestionnaire peut ensuite définir l'argument en `FALSE` pour indiquer qu'il n'est pas géré un message.  Dans ce cas, ATL continue à rechercher une fonction gestionnaire plus loin dans la table des messages.  En définissant cet argument à `FALSE`, vous pouvez d'abord exécuter une action en réponse à un message puis permettre le traitement de la valeur par défaut ou une fonction gestionnaire différent à la fin de le message.  
  
## Tables des messages liées  
 ATL vous permet également aux tables des messages à chaînes, qui dirige la gestion des messages à une table des messages définie dans une autre classe.  Par exemple, vous pouvez implémenter la gestion des messages commune dans une classe distincte pour fournir le comportement uniforme pour toutes les fenêtres chaînant à cette classe.  Vous pouvez enchaîner à une classe de base ou à une donnée membre de votre classe.  
  
 ATL prend également en charge le chaînage dynamique, qui vous permet à la chaîne à la table des messages d'un autre objet au moment de l'exécution.  Pour implémenter le chaînage dynamique, vous devez dériver votre classe de [CDynamicChain](../atl/reference/cdynamicchain-class.md).  Déclarez la macro de [CHAIN\_MSG\_MAP\_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md) dans votre table des messages.  `CHAIN_MSG_MAP_DYNAMIC` requiert un nombre unique qui identifie l'objet et la table des messages auxquels vous chaînez.  Vous devez définir cette valeur unique via un appel à `CDynamicChain::SetChainEntry`.  
  
 Vous pouvez enchaîner à toute classe qui déclare une table des messages, si la classe dérive de [CMessageMap](../atl/reference/cmessagemap-class.md).  `CMessageMap` permet à un objet d'exposer ses tables des messages à d'autres objets.  Notez qu' `CWindowImpl` dérive déjà d' `CMessageMap`.  
  
## Tables des messages secondaires  
 Enfin, les tables des messages secondaires de prises en charge ATL, déclarées avec la macro d' [ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md) .  Chaque table des messages secondaire est identifiée par un numéro unique, que vous passez à `ALT_MSG_MAP`.  Utilisation de tables des messages secondaires, vous pouvez gérer les messages de plusieurs fenêtres dans une carte.  Notez que par défaut, `CWindowImpl` n'utilise pas les tables des messages secondaires.  Pour ajouter cette prise en charge, remplacez la méthode d' `WindowProc` dans votre `CWindowImpl`classe dérivée de et appelez `ProcessWindowMessage` avec l'identificateur de la table des messages.  
  
## Voir aussi  
 [Implementing a Window](../atl/implementing-a-window.md)