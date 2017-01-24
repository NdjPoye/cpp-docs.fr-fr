---
title: "Contr&#244;les ActiveX MFC&#160;: &#233;v&#233;nements | Microsoft Docs"
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
  - "COleControl (classe), gestion des événements"
  - "conteneurs (événements)"
  - "événements personnalisés, ajouter aux contrôles ActiveX"
  - "événements (C++), contrôles ActiveX"
  - "événements (C++), mapper"
  - "mappages, événements"
  - "contrôles ActiveX MFC, événements"
  - "notifications (C++), notifier des conteneurs d'événements"
  - "événements OLE"
  - "événements stock"
ms.assetid: e1e57e0c-206b-4923-a0b5-682c26564f74
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: &#233;v&#233;nements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les contrôles ActiveX utilisent des événements pour avertir un conteneur que quelque chose est arrivé au contrôle.  Les exemples classiques d'événements incluent les clics sur le contrôle, les entrées de données utilisant le clavier, et les modifications de l'état du contrôle.  Lorsque ces actions se produisent, le contrôle déclenche un événement pour avertir le conteneur.  
  
 Les événements sont également appelés messages.  
  
 MFC prend en charge deux types d'événements : actions et personnalisés.  Les événements Stock sont les événements qui classent les gestions de [COleControl](../mfc/reference/colecontrol-class.md) automatiquement.  Pour obtenir une liste complète des événements Stock, consultez l'article [Contrôles ActiveX MFC : Ajouter des événements Stock](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md).  Les événements personnalisés permettent un contrôle de la capacité à informer le conteneur lorsqu'une action spécifique à ce contrôle se produit.  Certains exemples seront une modification dans l'état interne d'un contrôle ou de la réception d'une fenêtre d'information.  
  
 Pour que le contrôle déclenche les événements correctement, votre classe de contrôle doit associer chaque événement du contrôle à une fonction membre qui doit être appelée lorsque l'événement associé se produit.  Ce mécanisme de mappage \(appelé table d'événement\) centralise des informations sur l'événement et Visual Studio permet d'accéder facilement et manipule les événements du contrôle.  Cette table d'événements est déclarée par la macro suivante, placée dans le fichier d'en\-tête \(.H\) de la déclaration de classe de contrôle :  
  
 [!code-cpp[NVC_MFC_AxUI#2](../mfc/codesnippet/CPP/mfc-activex-controls-events_1.h)]  
  
 Une fois la table d'événements déclarée, elle doit être définie dans le fichier \(.CPP\) à l'implémentation de votre contrôle.  Les lignes suivantes du code définissent la table d'événement, qui permet le contrôle des événements spécifiques de l'exécution :  
  
 [!code-cpp[NVC_MFC_AxUI#3](../mfc/codesnippet/CPP/mfc-activex-controls-events_2.cpp)]  
[!code-cpp[NVC_MFC_AxUI#4](../mfc/codesnippet/CPP/mfc-activex-controls-events_3.cpp)]  
  
 Si vous utilisez l'Assistant Contrôle ActiveX MFC pour créer le projet, il ajoute automatiquement ces lignes.  Si vous n'utilisez pas le Contrôle ActiveX MFC, vous devez ajouter manuellement ces lignes.  
  
 Avec l'Affichage de classe, vous pouvez ajouter des événements stock pris en charge par la classe `COleControl` ou des événements personnalisés que vous définissez.  Pour chaque nouvel événement, l'Affichage de classe ajoute automatiquement l'entrée correspondant à la table d'événement du contrôle et le fichier .IDL du contrôle.  
  
 Deux autres articles traitent des événements en détail :  
  
-   [MFC Contrôles d'ActiveX : Ajout d'événements stock](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [Contrôles ActiveX MFC : ajout d'événements personnalisés](../mfc/mfc-activex-controls-adding-custom-events.md)  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Contrôles ActiveX MFC : méthodes](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)