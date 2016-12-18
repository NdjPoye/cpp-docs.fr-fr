---
title: "Creating a 256-Color Icon or Cursor (Image Editor for Icons) | Microsoft Docs"
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
  - "256-color palette"
  - "cursors, color"
  - "colors, icons"
  - "colors, cursors"
  - "icons, color"
ms.assetid: 2738089b-4fd3-4c45-96ae-6a15e4c6b780
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a 256-Color Icon or Cursor (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En utilisant l'Éditeur d'images, les icônes et les curseurs peuvent être de grande taille \(64 x 64\) avec une palette de 256 couleurs.  Après avoir créé la ressource, un style d'image de périphérique est sélectionné.  
  
### Pour créer une icône ou un curseur 256 couleurs  
  
1.  Dans l'[Affichage des ressources](../windows/resource-view-window.md), cliquez avec le bouton droit sur votre fichier .rc, puis sur **Ajouter une ressource** dans le menu contextuel.  \(Si vous disposez déjà d'une ressource image dans votre fichier .rc, par exemple un curseur, vous pouvez cliquer avec le bouton droit sur le dossier **Cursor** et sélectionnez **Insérer Cursor** dans le menu contextuel.\)  
  
     **Remarque** Si votre projet ne contient pas déjà de fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Dans la [boîte de dialogue Ajouter une ressource](../windows/add-resource-dialog-box.md), sélectionnez **Icône** ou **Curseur**, puis cliquez sur **Nouveau**.  
  
3.  Dans le menu **Image**, cliquez sur **Nouveau type d'image**.  
  
4.  Sélectionnez le style d'image 256 couleurs souhaité.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Configuration requise**  
  
 Aucun  
  
## Voir aussi  
 [Using the 256\-Color Palette](../mfc/using-the-256-color-palette-image-editor-for-icons.md)   
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)