---
title: "Working with Color (Image Editor for Icons) | Microsoft Docs"
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
  - "vc.editors.image.color"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "images [C++], background colors"
  - "Image editor [C++], Colors Palette"
  - "colors [C++], image"
  - "Colors Palette, Image editor"
  - "palettes, Image editor colors"
  - "foreground colors, Image editor"
  - "colors [C++]"
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Working with Color (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'Éditeur d'images contient de nombreuses fonctionnalités qui permettent de gérer et de personnaliser les couleurs.  Vous pouvez définir une couleur de premier plan ou d'arrière\-plan, remplir les zones délimitées par une couleur ou sélectionner une couleur dans une image à utiliser comme couleur de premier plan ou d'arrière\-plan.  Vous pouvez utiliser les outils de la [barre d'outils Éditeur d'images](../mfc/toolbar-image-editor-for-icons.md) avec la palette de couleurs de la [fenêtre Couleurs](../windows/colors-window-image-editor-for-icons.md) pour créer des images.  
  
 Toutes les couleurs pour les images monochromes et 16 couleurs sont affichées dans la palette Couleurs de la fenêtre Couleurs.  En plus des 16 couleurs standard, vous pouvez créer vos propres couleurs personnalisées.  La modification d'une couleur dans la palette, change immédiatement la couleur correspondante dans l'image.  
  
 Lorsque vous travaillez avec des images icône et curseur 256 couleurs, la propriété Colors de la [fenêtre Propriétés](../Topic/Properties%20Window.md) est utilisée.  Pour plus d'informations, consultez [Création d'une icône ou d'un curseur 256 couleurs](../mfc/creating-a-256-color-icon-or-cursor-image-editor-for-icons.md).  
  
> [!NOTE]
>  Grâce à l'Éditeur d'images, vous pouvez afficher des images 32 bits, mais vous ne pouvez pas les modifier.  
  
 Des images en couleurs vraies peuvent également être créées.  Cependant, les exemples de couleurs vraies ne s'affichent pas dans la palette de la fenêtre Couleurs ; ils s'affichent uniquement dans la zone qui indique la couleur de premier plan ou d'arrière\-plan.  Les couleurs vraies sont créées en utilisant la [boîte de dialogue Affiner les couleurs](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md).  Pour plus d'informations, consultez [Personnalisation ou modification des couleurs](../windows/customizing-or-changing-colors-image-editor-for-icons.md).  
  
 Vous pouvez enregistrer des palettes de couleurs personnalisées sur disque et les recharger quand vous en avez besoin.  La palette de couleurs que vous avez utilisée le plus récemment est enregistrée dans le Registre et chargée automatiquement lorsque vous démarrez Visual Studio.  
  
-   [Sélection de couleurs de premier plan ou d'arrière\-plan](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)  
  
-   [Remplissage avec une couleur d'une zone délimitée d'une image](../windows/filling-a-bounded-area-of-an-image-with-a-color-image-editor-for-icons.md)  
  
-   [Sélection d'une couleur dans une image à utiliser ailleurs](../windows/picking-up-a-color-from-an-image-to-use-elsewhere-image-editor-for-icons.md)  
  
-   [Choix d'un arrière\-plan transparent ou opaque](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)  
  
-   [Inversion des couleurs dans une sélection](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)  
  
-   [Personnalisation ou modification des couleurs](../windows/customizing-or-changing-colors-image-editor-for-icons.md)  
  
-   [Enregistrement et chargement de différentes palettes de couleurs](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)  
  
-   [Fenêtre Couleurs](../windows/colors-window-image-editor-for-icons.md)  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Configuration requise  
 Aucun  
  
## Voir aussi  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Ressources](_win32_Resources)