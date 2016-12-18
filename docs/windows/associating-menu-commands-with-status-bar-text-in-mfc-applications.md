---
title: "Associating Menu Commands with Status Bar Text in MFC Applications | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "status bars, associating menu items"
  - "menus, status bar text"
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Associating Menu Commands with Status Bar Text in MFC Applications
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Votre application peut afficher un texte descriptif pour chacune des commandes de menu qu'un utilisateur peut sélectionner. Pour ce faire, assignez une chaîne de texte à chaque commande de menu à l'aide de la propriété **Invite** dans la fenêtre Propriétés. Si vous avez une chaîne dans la [table de chaînes](../mfc/string-editor.md) dont l'ID est identique à la commande, une application MFC affiche automatiquement cette ressource de chaîne dans la barre d'état de l'application en cours d'exécution quand un utilisateur pointe sur un élément de menu.  
  
### Pour associer une commande de menu à une chaîne de texte de barre d'état  
  
1.  Dans l'**éditeur de menus**, sélectionnez la commande de menu.  
  
2.  Dans la [fenêtre Propriétés](../Topic/Properties%20Window.md), tapez le texte de barre d'état associé dans la zone **Invite**.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, consultez [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Spécifications**  
  
 MFC  
  
## Voir aussi  
 [Chaînes](../atl-mfc-shared/strings-atl-mfc.md)   
 [Adding Commands to a Menu](../windows/adding-commands-to-a-menu.md)   
 [Menu Editor](../mfc/menu-editor.md)