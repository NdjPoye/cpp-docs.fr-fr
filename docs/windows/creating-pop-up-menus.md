---
title: "Creating Pop-up Menus | Microsoft Docs"
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
  - "context menus, Menu Editor"
  - "pop-up menus, creating"
  - "menus, pop-up"
  - "menus, creating"
  - "shortcut menus, creating"
  - "pop-up menus, displaying"
ms.assetid: dff4dddf-2e8d-4c34-b755-90baae426b58
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating Pop-up Menus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les [menus contextuels](../mfc/menus-mfc.md) affichent les commandes fréquemment utilisées. Ils dépendent du contexte selon l'emplacement du pointeur. L'utilisation de menus contextuels dans votre application nécessite la création du menu en question, puis sa connexion au code de l'application.  
  
 Une fois que vous avez créé la ressource de menu, votre code d’application doit charger cette ressource et utiliser [TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) pour faire apparaître le menu. Une fois que l'utilisateur a fermé le menu contextuel en cliquant hors de ce dernier, ou qu'il a cliqué sur une commande, cette fonction est retournée. Si l'utilisateur choisit une commande, ce message de commande est envoyé à la fenêtre dont le handle a été passé.  
  
### Pour créer un menu contextuel  
  
1.  [Créez un menu](../windows/creating-a-menu.md) avec un titre vide \(ne fournissez pas de **légende**\).  
  
2.  [Ajoutez une commande de menu au nouveau menu](../windows/adding-commands-to-a-menu.md). Placez\-vous sur la première commande de menu sous le titre de menu vide \(la légende temporaire indique « Tapez ici »\). Tapez une **légende** et les autres informations appropriées.  
  
     Répétez ce processus pour les autres commandes de menu du menu contextuel.  
  
3.  Enregistrez la ressource de menu.  
  
    > [!TIP]
    >  Pour plus d'informations sur l'affichage du menu contextuel, voir [Affichage d'un menu sous la forme d'un menu contextuel](../windows/viewing-a-menu-as-a-pop-up-menu.md).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, consultez [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Spécifications**  
  
 Win32  
  
## Voir aussi  
 [Connecting a Pop\-up Menu to Your Application](../windows/connecting-a-pop-up-menu-to-your-application.md)   
 [Menu Editor](../mfc/menu-editor.md)