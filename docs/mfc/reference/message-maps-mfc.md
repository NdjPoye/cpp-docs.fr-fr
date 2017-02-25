---
title: "Tables des messages (MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tables des messages (C++), MFC"
  - "messages (C++), Windows"
  - "MFC (C++), messages"
  - "messages Windows (C++), tables des messages"
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Tables des messages (MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette section de référence liste toutes les [macros de mappage de message](../../mfc/reference/message-map-macros-mfc.md) et toutes les entrées de la table des messages [CWnd](../../mfc/reference/cwnd-class.md) avec les prototypes correspondants de fonction membre :  
  
|Catégorie|Description|  
|---------------|-----------------|  
|[WM\_COMMAND, gestionnaire de messages](../../mfc/reference/wm-command-message-handler.md)|Messages **WM\_COMMAND** de handles générés par les sélections d'utilisateur ou des touches d'accès rapide de menu.|  
|[Gestionnaires pour les messages de notification de fenêtre enfant](../../mfc/reference/child-window-notification-message-handlers.md)|Messages de notification de gestion des fenêtres enfants.|  
|[gestionnaires des messages WM](../../mfc/reference/handlers-for-wm-messages.md)|Messages **WM\_** de handles, tels que `WM_PAINT`.|  
|[Gestionnaires de message défini par l'utilisateur](../../mfc/reference/user-defined-handlers.md)|Messages définis par l'utilisateur de handle.|  
  
 \(Pour une explication de la terminologie et conventions utilisés dans cette référence, consultez [Comment utiliser le renvoi de table des messages](../../mfc/reference/how-to-use-the-message-map-cross-reference.md).\)  
  
 Puisque Windows est un système d'exploitation orienté vers les messages, une grande partie de la programmation de l'environnement Windows concerne la gestion des messages.  Chaque fois qu'un événement tel qu'une séquence ou un clic de souris se produit, un message est envoyé à l'application, qui doit ensuite gérer l'événement.  
  
 La bibliothèque MFC fournit un modèle de programmation optimisé pour la programmation par base.  Dans ce modèle, les « tables des messages » sont utilisées pour indiquer quelles fonctions traiteront les différents messages pour une classe particulière.  Les tables des messages contiennent une ou plusieurs macros qui déterminent quels messages seront gérés par ces fonctions.  Par exemple, une table des messages contenant une macro `ON_COMMAND` peut ressembler à ceci :  
  
 [!code-cpp[NVC_MFCMessageMaps#16](../../mfc/reference/codesnippet/CPP/message-maps-mfc_1.cpp)]  
  
 La macro pour `ON_COMMAND` est utilisée pour traiter des messages de commande générés par des menus, des boutons, et de touches accélérateur.  [Macros](../../mfc/reference/message-map-macros-mfc.md) sont disponibles pour mapper les opérations suivantes :  
  
## messages Windows  
  
-   notification de contrôle  
  
-   Messages définis par l'utilisateur  
  
## OCM\_COMMAND \(message\)  
  
-   Messages enregistrés et définis par l'utilisateur  
  
-   Messages de mise à jour de l'interface utilisateur  
  
## Plages des messages  
  
-   Commandes  
  
-   Messages de gestionnaire de mise à jour  
  
-   notification de contrôle  
  
 Bien que les macros de table des messages soient importantes, vous ne devez pas les utiliser directement.  Ceci car la fenêtre Propriétés crée automatiquement des entrées de la table des messages dans vos fichiers sources lorsque vous l'utilisez pour associer des fonctions de gestion de messages avec des messages.  Lorsque vous souhaitez modifier ou ajouter une entrée dans la table des messages, utilisez la fenêtre Propriétés.  
  
> [!NOTE]
>  La fenêtre Propriétés ne prend pas en charge les plages de table des messages.  Vous devez écrire ces entrées de la table des messages vous\-même.  
  
 Toutefois, les tables des messages représentent une proportion significative de la bibliothèque MFC.  Vous devez comprendre ce qu'ils contiennent, et de la documentation est fournie pour celles\-ci.  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)