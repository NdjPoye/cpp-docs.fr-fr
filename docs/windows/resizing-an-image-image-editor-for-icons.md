---
title: "Resizing an Image (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.image.editing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Image editor [C++], resizing images"
  - "graphics [C++], resizing"
  - "images [C++], resizing"
  - "resizing images"
ms.assetid: d83a02c4-4dfe-4586-a0df-51a50c2ba71d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Resizing an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le comportement de l'Éditeur d'images lors du redimensionnement d'une image dépend de la [sélection](../mfc/selecting-an-area-of-an-image-image-editor-for-icons.md) \(intégralité de l'image ou une partie\).  
  
 Lorsque la sélection ne comprend qu'une partie de l'image, l'Éditeur d'images réduit la sélection en supprimant des lignes ou des colonnes de pixels et en remplissant les régions libérées avec la couleur d'arrière\-plan actuelle ou il étire la sélection en dupliquant des lignes ou des colonnes de pixels.  
  
 Lorsque la sélection comprend l'intégralité de l'image, l'Éditeur d'images réduit ou étire l'image ou bien rogne ou étend l'image.  
  
 Il existe deux mécanismes pour redimensionner une image : les poignées de redimensionnement et la [fenêtre Propriétés](../Topic/Properties%20Window.md).  Vous pouvez faire glisser les poignées de redimensionnement pour changer la taille d'une partie ou de l'intégralité d'une image.  Les poignées de redimensionnement que vous pouvez faire glisser sont pleines.  Vous ne pouvez pas faire glisser des poignées qui sont vides.  Vous ne pouvez utiliser la fenêtre Propriétés que pour redimensionner l'intégralité d'une image.  
  
 ![Poignées de dimensionnement d'une image bitmap](../mfc/media/vcimageeditorsizinghandles.png "vcImageEditorSizingHandles")  
Poignées de redimensionnement  
  
> [!NOTE]
>  Si l'option Grille mosaïque est sélectionnée dans la [boîte de dialogue Paramètres de la grille](../mfc/grid-settings-dialog-box-image-editor-for-icons.md), l'image lors du redimensionnement s'aligne sur le quadrillage suivant.  Si seule l'option Grille de pixels est sélectionnée \(paramètre par défaut\), l'image lors du redimensionnement s'aligne sur le pixel suivant.  
  
-   [Redimensionnement de l'intégralité d'une image](../mfc/resizing-an-entire-image-image-editor-for-icons.md)  
  
-   [Rognage ou extension de l'intégralité d'une image](../mfc/cropping-or-extending-an-entire-image-image-editor-for-icons.md)  
  
-   [Réduction ou étirement de l'intégralité d'une image](../mfc/shrinking-or-stretching-an-entire-image-image-editor-for-icons.md)  
  
-   [Réduction ou étirement d'une partie d'une image](../mfc/shrinking-or-stretching-part-of-an-image-image-editor-for-icons.md)  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Configuration requise  
 Aucun  
  
## Voir aussi  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)