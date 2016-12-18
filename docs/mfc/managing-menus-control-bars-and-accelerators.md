---
title: "Gestion des menus, barres de contr&#244;le et acc&#233;l&#233;rateurs | Microsoft Docs"
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
  - "tables d'accélérateurs (C++)"
  - "barres de contrôles, mettre à jour dans des fenêtres frame"
  - "fenêtres frame, mettre à jour"
  - "MDI, fenêtres frame"
  - "menus, mettre à jour au fur et à mesure des changements de contexte"
  - "partager des menus"
  - "barres d'état, mettre à jour"
  - "mettre à jour des objets d'interface utilisateur"
  - "objets de l'interface utilisateur, mettre à jour"
ms.assetid: 97ca1997-06df-4373-b023-4f7ecd81047b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestion des menus, barres de contr&#244;le et acc&#233;l&#233;rateurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La fenêtre cadre gère la mise à jour des objets interface\-utilisateur, notamment les menus, les boutons de la barre d'outils, la barre d'état, et des accélérateurs.  Il gère également le partage de la barre de menus dans les applications MDI.  
  
## Gestion des menus  
 La fenêtre cadre participe à la mise à jour des éléments d'interface utilisateur à l'aide du mécanisme de `ON_UPDATE_COMMAND_UI` décrit dans [Procédure objets interface utilisateur de mise à jour](../mfc/how-to-update-user-interface-objects.md).  Les boutons des barres d'outils et d'autres barres de contrôles sont mises à jour pendant la boucle inactive.  Les éléments du menu dans les menus déroulants dans la barre de menus sont mis à jour juste avant le menu "supprimer" déroulante.  
  
 Pour les applications MDI, la fenêtre cadre MDI gère la barre de menus et la légende.  Une fenêtre cadre MDI possède un menu par défaut utilisé comme barre de menus lorsqu'il n'y a aucune fenêtre enfant MDI active.  Lorsqu'il existe des enfants actifs, la barre de menus de la fenêtre cadre MDI est assurée par le menu pour les fenêtres enfants MDI activé.  Si un type de document multiple sous support d'application MDI, tels que le graphique et les documents de feuille de calcul, chaque type met ses propres menus dans la barre de menus et modifie la légende de la fenêtre principale cadre.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) offre des implémentations conformes par défaut des commandes standard dans le menu Fenêtre qui s'affiche pour les applications MDI.  En particulier, la commande nouvelle fenêtre \(**ID\_WINDOW\_NEW**\) est implémentée pour créer une nouvelle fenêtre cadre et une vue dans le document actif.  Vous devez substituer les implémentations uniquement si vous avez besoin de personnalisation avancée.  
  
 Plusieurs fenêtres enfants MDI du même type de document partagent des ressources menu.  Si plusieurs fenêtres enfants MDI sont créées par le même modèle de document, elles peuvent toutes utiliser la même ressource menu, en réalisant l'enregistrement sur les ressources système de windows.  
  
## Gère la barre d'état.  
 La fenêtre cadre positionne également la barre d'état dans la zone client et gère les indicateurs de barre d'état.  La fenêtre cadre désactive et met à jour la zone message dans la barre d'état si nécessaire et affiches des caractères sans faute lorsque l'utilisateur sélectionne les éléments du menu ou des boutons de la barre d'outils, comme décrit dans [Comment afficher les informations de commande dans la barre d'état](../mfc/how-to-display-command-information-in-the-status-bar.md).  
  
## Gestion des accélérateurs  
 Chaque fenêtre cadre contient une table d'accélérateurs facultative qui effectue la traduction des accélérateurs clavier automatiquement.  Ce mécanisme rend ainsi plus simple à définir les touches accélérateur \(également appelées touches de raccourci\) qui appellent des commandes de menu.  
  
## Voir aussi  
 [Utilisation de fenêtres frame](../mfc/using-frame-windows.md)