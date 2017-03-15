---
title: "Using the 256-Color Palette (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "colors, icons and cursors"
  - "cursors, color"
  - "color palettes, 256-color"
  - "palettes, 256-color"
  - "icons, color"
ms.assetid: 1506ed00-669b-4a21-b1a4-39b6a84a78bb
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Using the 256-Color Palette (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour dessiner avec une sélection à partir de la palette 256 couleurs, vous devez sélectionner les couleurs à partir de la palette Couleurs dans la [fenêtre Couleurs](../windows/colors-window-image-editor-for-icons.md).  
  
### Pour choisir une couleur à partir de la palette 256 couleurs pour de grandes icônes  
  
1.  Sélectionnez une grande icône ou un grand curseur ou créez une nouvelle grande icône ou curseur.  
  
2.  Choisissez une couleur parmi les 256 affichées dans la palette **Couleurs** de la fenêtre **Couleurs**.  
  
     La couleur sélectionnée devient la couleur actuelle dans la palette Couleurs de la fenêtre **Couleurs**.  
  
    > [!NOTE]
    >  La palette d'origine utilisée pour les images 256 couleurs correspond à la palette retournée par l'API Windows CreateHalftonePalette.  Toutes les icônes pour le shell Windows doivent utiliser cette palette pour empêcher le scintillement lors de la réalisation de la palette.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 Aucun  
  
## Voir aussi  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Creating a 256\-Color Icon or Cursor](../mfc/creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)