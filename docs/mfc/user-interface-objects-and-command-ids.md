---
title: "Objets d&#39;interface utilisateur et ID de commande | Microsoft Docs"
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
  - "gestion des commandes, objets d'interface utilisateur"
  - "ID de commande, objets de l'interface utilisateur"
  - "routage des commandes, MFC"
  - "raccourcis clavier, associer à des ID"
  - "éléments de menu, associer à des ID"
  - "MFC, routage des commandes"
  - "contrôles de barre d'outils (MFC), ID de commande"
  - "objets de l'interface utilisateur, associer à des ID"
ms.assetid: 4ea19e9b-ed1e-452e-bd33-7f509107a45b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Objets d&#39;interface utilisateur et ID de commande
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les éléments de menu, les boutons de la barre d'outils, et les touches accélérateur sont des « objets d'interface utilisateur » pouvant générer des commandes.  Chaque objet d'interface utilisateur de ce type a un ID  Vous associez un objet d'interface utilisateur avec une commande en assignant le même ID à l'objet et à la commande.  Comme expliqué dans [Messages](../mfc/messages.md), les commandes sont implémentées en tant que messages spéciaux.  La figure « Commandes dans l'infrastructure » ci\-dessous montre comment l'infrastructure gère les commandes.  Lorsqu'un objet d'interface utilisateur produit une commande, telle que `ID_EDIT_CLEAR_ALL`, l'un des objets dans votre application gère la commande — dans la figure ci\-dessous, la fonction `OnEditClearAll` de l'objet document est appelée par le biais de la table des messages du document.  
  
 ![Commandes dans le Framework](../mfc/media/vc385p1.png "vc385P1")  
Commandes dans le Framework  
  
 L'illustration « Mise à jour des commandes dans l'infrastructure » ci\-dessous indique comment MFC met à jour des objets d'interface utilisateur tels que les éléments de menu et les boutons de la barre d'outils.  Avant qu'un menu ne se déroule, ou pendant la boucle inactive dans le cas des boutons de la barre d'outils, MFC fait circuler une commande de mise à jour.  Dans l'illustration ci\-dessous, l'objet document appelle le gestionnaire de commandes de mise à jour, `OnUpdateEditClearAll`, pour activer ou désactiver l'objet interface utilisateur.  
  
 ![Mise à jour des commandes dans le Framework](../mfc/media/vc385p2.png "vc385P2")  
Mise à jour des commandes dans l'interface  
  
## Voir aussi  
 [Messages et commandes dans le Framework](../mfc/messages-and-commands-in-the-framework.md)