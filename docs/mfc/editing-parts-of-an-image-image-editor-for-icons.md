---
title: "Editing Parts of an Image (Image Editor for Icons) | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "Image editor [C++], editing images"
  - "Clipboard [C++], pasting"
  - "images [C++], editing"
  - "images [C++], deleting selected parts"
  - "images [C++], copying selected parts"
  - "images [C++], moving selected parts"
  - "images [C++], dragging and replicating selected parts"
  - "images [C++], pasting into"
  - "graphics [C++], editing"
ms.assetid: ff4f5fef-71a4-4fd8-825e-049399fed391
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Editing Parts of an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez effectuer des opérations de modification standard \(couper, copier, effacer et déplacer\) sur une [sélection](../mfc/selecting-an-area-of-an-image-image-editor-for-icons.md), qu'il s'agisse de l'intégralité de l'image ou d'une partie.  Dans la mesure où l'éditeur d'images utilise les fenêtres presse\-papiers, vous pouvez transférer des images entre l'éditeur d'images et d'autres applications pour Windows.  
  
 De plus, vous pouvez redimensionner la sélection, qu'il s'agisse de l'intégralité d'une image ou d'une partie.  
  
### Pour couper la sélection actuelle et la déplacer dans le Presse\-papiers  
  
1.  Dans le menu **Edition**, cliquez sur **Couper**.  
  
### Pour copier la sélection  
  
1.  Placez le pointeur à l'intérieur de la bordure de sélection ou n'importe où sur la bordure à l'exception des poignées de redimensionnement.  
  
2.  Maintenez la touche **CTRL** enfoncée tout en faisant glisser la sélection vers un nouvel emplacement.  La zone de la sélection d'origine reste inchangée.  
  
3.  Pour copier la sélection dans l'image à l'emplacement actuel, cliquez en dehors du curseur de sélection.  
  
### Pour coller le contenu du Presse\-papiers dans une image  
  
1.  Dans le menu **Edition**, choisissez **Coller**.  
  
     Le contenu du Presse\-papiers, entouré par la bordure de sélection, s'affiche dans le coin supérieur gauche du volet.  
  
2.  Placez le pointeur à l'intérieur de la bordure de sélection et faites glisser l'image vers l'emplacement souhaité sur l'image.  
  
3.  Pour ancrer l'image à son nouvel emplacement, cliquez en dehors de la bordure de sélection.  
  
### Pour supprimer la sélection actuelle sans la placer dans le Presse\-papiers  
  
1.  Dans le menu **Edition**, cliquez sur **Supprimer**.  
  
     La zone d'origine de la sélection est remplie avec la couleur d'arrière\-plan actuelle.  
  
    > [!NOTE]
    >  Vous pouvez accéder aux commandes Couper, Copier, Coller et Supprimer en cliquant avec le bouton droit dans la fenêtre Affichage des ressources.  
  
### Pour déplacer la sélection  
  
1.  Placez le pointeur à l'intérieur de la bordure de sélection ou n'importe où sur la bordure à l'exception des poignées de redimensionnement.  
  
2.  Faites glisser la sélection vers son nouvel emplacement.  
  
3.  Pour ancrer la sélection dans l'image à son nouvel emplacement, cliquez en dehors de la bordure de sélection.  
  
 Pour plus d'informations sur le dessin avec une sélection, consultez [Création d'un pinceau personnalisé](../mfc/creating-a-custom-brush-image-editor-for-icons.md).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 Aucun  
  
## Voir aussi  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)