---
title: "Associating a Menu Command with an Accelerator Key | Microsoft Docs"
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
  - "keyboard shortcuts, menu association"
  - "commands, associating menu commands with accelerator keys"
  - "menu commands, associating with keyboard shortcuts"
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Associating a Menu Command with an Accelerator Key
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bien souvent, vous souhaitez qu’une commande de menu et une combinaison de touches du clavier exécutent la même commande de programme. Pour cela, vous utilisez l’Éditeur de menus pour assigner le même identificateur de ressource à la commande de menu et à une entrée dans la table d’accélérateurs de votre application. Ensuite, vous modifiez la [Légende](../windows/menu-command-properties.md) de la commande de menu pour afficher le nom de la touche accélérateur.  
  
### Pour associer une commande de menu à une touche accélérateur  
  
1.  Dans l’**Éditeur de menus**, sélectionnez la commande de menu souhaitée.  
  
2.  Dans la fenêtre [Propriétés](../Topic/Properties%20Window.md), ajoutez le nom de la touche accélérateur à la propriété **Légende** :  
  
    -   À la suite de la légende de menu, tapez la séquence d’échappement d’une tabulation \(\\t\) pour que toutes les touches accélérateurs du menu soient alignées à gauche.  
  
    -   Tapez le nom de la touche de modification \(**Ctrl**, **Alt** ou **Maj**\) suivi d’un signe plus \(**\+**\) et du nom, de la lettre ou du symbole de l’autre touche.  
  
         Par exemple, pour attribuer **Ctrl\+O** à la commande **Ouvrir** du menu **Fichier**, vous devez modifier la **Légende** de la commande de menu pour qu’elle ressemble à ceci :  
  
        ```  
        &Open...\tCtrl+O   
        ```  
  
         La commande de menu dans l’Éditeur de menus est mise à jour pour refléter la nouvelle légende à mesure que vous la tapez.  
  
3.  [Créez l’entrée de table d’accélérateurs](../windows/adding-an-entry-to-an-accelerator-table.md) dans l’éditeur d’**accélérateurs** et attribuez\-lui le même identificateur que la commande de menu. Utilisez une combinaison de touches facile à mémoriser.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Spécifications**  
  
 Win32  
  
## Voir aussi  
 [Adding Commands to a Menu](../windows/adding-commands-to-a-menu.md)   
 [Menu Editor](../mfc/menu-editor.md)