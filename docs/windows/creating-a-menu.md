---
title: "Creating a Menu | Microsoft Docs"
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
  - "mnemonics, associating menu items"
  - "menus, associating commands with mnemonic keys"
  - "menus, creating"
ms.assetid: 66f94448-9b97-4b73-bf97-10d4bf87cc65
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a Menu
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La fenêtre Ressources n’est pas disponible dans les éditions Express.  
  
### Pour créer un menu standard  
  
1.  Dans le menu **Affichage**, cliquez sur **Affichage des ressources**, puis cliquez avec le bouton droit sur l’en\-tête **Menu** et choisissez **Ajouter une ressource**. Choisissez **Menu**.  
  
2.  Sélectionnez la zone **Nouvel élément** \(le rectangle qui contient « Tapez ici »\) dans la barre de menus.  
  
     ![Zone Nouvel élément de l'éditeur de menus](../windows/media/vcmenueditornewitembox.png "vcMenuEditorNewItemBox")  
Zone Nouvel élément  
  
3.  Tapez un nom pour votre nouveau menu, par exemple, « Fichier ».  
  
     Le texte que vous tapez s’affiche dans l’**Éditeur de menus** et dans la zone **Légende** de la fenêtre [Propriétés](../Topic/Properties%20Window.md). Vous pouvez modifier les propriétés du nouveau menu dans les deux emplacements.  
  
     Une fois que vous avez donné un nom à votre nouveau menu dans la barre de menus, la zone Nouvel élément se déplace vers la droite \(pour vous permettre d’ajouter un autre menu\) et une autre zone Nouvel élément s’ouvre sous votre premier menu pour que vous puissiez y ajouter des commandes de menu.  
  
     ![Zone Nouvel élément développée](../windows/media/vcmenueditornewitemboxexpanded.png "vcMenuEditorNewItemBoxExpanded")  
Zone Nouvel élément avec déplacement du focus quand vous avez tapé le nom du menu  
  
    > [!NOTE]
    >  Pour créer un menu à un seul élément dans la barre de menus, affectez la valeur False à la propriété Popup.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Spécifications**  
  
 Win32  
  
## Voir aussi  
 [Menu Editor](../mfc/menu-editor.md)