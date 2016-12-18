---
title: "Creating a New Toolbar Button | Microsoft Docs"
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
  - "vc.editors.toolbar"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "Toolbar editor, creating buttons"
  - "toolbar buttons (in Toolbar editor), button image"
  - "toolbar buttons (in Toolbar editor), creating"
  - "toolbar buttons (in Toolbar editor)"
ms.assetid: 46c120fe-4f2a-4887-a08f-bd1fea04b3f4
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a New Toolbar Button
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Pour créer un nouveau bouton de barre d'outils  
  
1.  Dans l'[Affichage des ressources](../windows/resource-view-window.md) développez le dossier des ressources \(par exemple, Project1.rc\).  
  
    > [!NOTE]
    >  Si votre projet ne contient pas encore de fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Développez le dossier **Toolbar** et sélectionnez une barre d'outils à modifier.  
  
3.  Assignez un ID au bouton vide à l'extrémité droite de la barre d'outils.  Pour ce faire, vous pouvez modifier la propriété **ID** dans la [fenêtre Propriétés](../Topic/Properties%20Window.md).  Par exemple, vous pouvez donner à un bouton de barre d'outils le même ID qu'une option de menu.  Dans ce cas, utilisez la zone de liste déroulante modifiable pour sélectionner l'**ID** de l'option de menu.  
  
     \- ou \-  
  
     Sélectionnez le bouton vide à l'extrémité droite de la barre d'outils \(dans le volet d'affichage de la barre d'outils\) et commencez à dessiner.  Un ID de commande de bouton par défaut est assigné \(ID\_BUTTON\<n\>\).  
  
 Vous pouvez également copier et coller une image sur une barre d'outils en tant que nouveau bouton.  
  
#### Pour ajouter une image à une barre d'outils en tant que bouton  
  
1.  Dans l'[Affichage des ressources](../windows/resource-view-window.md), ouvrez la barre d'outils en double\-cliquant dessus.  
  
2.  Ensuite, ouvrez l'image que vous souhaitez ajouter à votre barre d'outils.  
  
    > [!NOTE]
    >  Si vous ouvrez l'image dans Visual Studio, elle s'ouvrira dans l'Éditeur d'images.  Vous pouvez également ouvrir l'image dans d'autres programmes graphiques.  
  
3.  Dans le menu **Edition**, cliquez sur **Copier**.  
  
4.  Basculez dans votre barre d'outils en cliquant sur son onglet en haut de la fenêtre source.  
  
5.  Dans le menu **Edition**, choisissez **Coller**.  
  
     L'image s'affiche dans votre barre d'outils sous la forme d'un nouveau bouton.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Configuration requise  
 MFC ou ATL  
  
## Voir aussi  
 [Toolbar Button Properties](../mfc/toolbar-button-properties.md)   
 [Creating, Moving, and Editing Toolbar Buttons](../mfc/creating-moving-and-editing-toolbar-buttons.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)