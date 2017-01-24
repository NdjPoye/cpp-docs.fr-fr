---
title: "Creating Transparent or Inverse Regions in Device Images (Image Editor for Icons) | Microsoft Docs"
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
  - "cursors [C++], screen regions"
  - "inverse colors, device images"
  - "transparent regions, device images"
  - "transparency, device images"
  - "Image editor [C++], device images"
  - "inverse regions, device images"
  - "cursors [C++], transparent regions"
  - "screen colors"
  - "regions, transparent"
  - "icons [C++], transparent regions"
  - "display devices, transparent and screen regions"
  - "transparent regions in devices"
  - "regions, inverse"
  - "colors [C++], Image editor"
  - "device projects, transparent images"
  - "icons [C++], screen regions"
ms.assetid: a994954b-b039-4391-a535-58d1fa10fc3b
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating Transparent or Inverse Regions in Device Images (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans l'[Éditeur d'images](../mfc/image-editor-for-icons.md), l'image d'icône ou de curseur par défaut a un attribut transparent.  Bien que les images d'icône et de curseur soient rectangulaires, elles ne s'affichent pas ainsi car certaines parties de l'image sont transparentes ; l'image sous\-jacente à l'écran se voit au travers de l'icône ou du curseur.  Lorsque vous faites glisser une icône, des parties de l'image peuvent s'afficher dans une couleur inversée.  Vous créez cet effet en définissant la couleur de l'écran et en inversant la couleur dans la [fenêtre Couleurs](../windows/colors-window-image-editor-for-icons.md).  
  
 La couleur de l'écran et la couleur inversée que vous appliquez aux icônes et aux curseurs forment et colorient l'image dérivée ou désignent les régions inversées.  Les couleurs indiquent les parties de l'image qui possèdent ces attributs.  Vous pouvez changer les couleurs qui représentent les attributs couleur de l'écran et couleur inversée.  Ces modifications n'ont pas de conséquence sur l'apparence de l'icône ou du curseur dans votre application.  
  
> [!NOTE]
>  Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée.  Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils**.  Pour plus d'informations, consultez [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/fr-fr/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Pour créer des régions transparentes ou inversées  
  
1.  Dans la fenêtre **Couleurs**, cliquez sur le sélecteur **Couleur d'écran** ou le sélecteur **Couleur inversée**.  
  
2.  Appliquez la couleur d'écran ou la couleur inversée à votre image à l'aide d'un outil de dessin.  Pour plus d'informations sur les outils de dessin, consultez [Using a Drawing Tool](../mfc/using-a-drawing-tool-image-editor-for-icons.md).  
  
### Pour changer la couleur de l'écran ou la couleur inversée  
  
1.  Sélectionnez le sélecteur **Couleur d'écran** ou le sélecteur **Couleur inversée**.  
  
2.  Choisissez une couleur dans la palette **Couleurs** de la fenêtre **Couleurs**.  
  
     La couleur complémentaire est automatiquement désignée pour l'autre sélecteur.  
  
    > [!TIP]
    >  Si vous double\-cliquez sur le sélecteur Couleur d'écran ou le sélecteur Couleur inversée, la [boîte de dialogue Affiner les couleurs](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md) s'affiche.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 Aucun  
  
## Voir aussi  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)