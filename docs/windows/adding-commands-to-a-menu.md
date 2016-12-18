---
title: "Adding Commands to a Menu | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.menu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "menu items, adding to menus"
  - "menus, adding items"
  - "commands, adding to menus"
  - "commands"
  - "menu items"
ms.assetid: 1523a755-0ab5-42f8-9e98-bb9881564431
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Commands to a Menu
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Pour ajouter des commandes à un menu  
  
1.  [Créez un menu](../windows/creating-a-menu.md).  
  
2.  Cliquez sur un nom de menu, par exemple, Fichier.  
  
     Chaque menu sera développé et exposera une zone Nouvel élément pour les commandes.  Par exemple, vous pouvez ajouter les commandes Nouveau, Ouvrir et Fermer à un menu Fichier.  
  
3.  Dans la zone Nouvel élément, tapez le nom de la nouvelle commande de menu.  
  
    > [!NOTE]
    >  Le texte que vous tapez s'affiche dans l'Éditeur de menus et dans la zone **Légende** de la [fenêtre Propriétés](../Topic/Properties%20Window.md).  Vous pouvez modifier les propriétés du nouveau menu dans les deux emplacements.  
  
    > [!TIP]
    >  Vous pouvez définir une touche mnémonique \(touche d'accès rapide\) qui permet à l'utilisateur de sélectionner la commande de menu.  Tapez une esperluette \(&\) devant une lettre pour spécifier qu'il s'agit de la touche mnémonique.  L'utilisateur peut sélectionner la commande de menu en tapant cette lettre.  
  
4.  Dans la fenêtre Propriétés, sélectionnez les propriétés de commande de menu qui s'appliquent.  Pour plus d'informations, voir [Propriétés d'une commande de menu](../windows/menu-command-properties.md).  
  
5.  Dans la zone **Invite** de la fenêtre Propriétés, tapez le message à afficher dans la barre d'état de votre application.  
  
     Cela crée une entrée dans la table de chaînes avec le même identificateur de ressource que la commande de menu que vous avez créée.  
  
    > [!NOTE]
    >  Les invites s'appliquent uniquement aux éléments de menu dont la propriété **Popup** a la valeur **True**.  Par exemple, les éléments de menu de niveau supérieur peuvent avoir des invites s'ils ont des éléments de sous\-menu.  Le but d'une invite est d'indiquer ce qui se passe si un utilisateur clique sur l'élément de menu.  
  
6.  Appuyez sur **Entrée** pour terminer la commande de menu.  
  
     La zone Nouvel élément est sélectionnée pour vous permettre de créer des commandes de menu supplémentaires.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Spécifications**  
  
 Win32  
  
## Voir aussi  
 [Menu Editor](../mfc/menu-editor.md)   
 [Menus](_win32_Menus)