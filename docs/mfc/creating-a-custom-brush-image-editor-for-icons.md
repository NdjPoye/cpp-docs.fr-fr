---
title: "Creating a Custom Brush (Image Editor for Icons) | Microsoft Docs"
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
  - "colors [C++], brush"
  - "brushes, colors"
  - "brushes, creating custom"
  - "images [C++], creating custom brushes"
  - "graphics [C++], custom brushes"
  - "custom brushes"
ms.assetid: 750881aa-6f47-4de9-8ca6-a7a12afc6383
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a Custom Brush (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un pinceau \(brush en anglais\) personnalisé est une partie rectangulaire d'une image que vous sélectionnez et utilisez comme l'un des pinceaux prédéfinis de l'Éditeur d'images.  Toutes les opérations que vous pouvez effectuer sur une sélection, vous pouvez également les effectuer sur un pinceau personnalisé.  
  
### Pour créer un pinceau personnalisé à partir d'une partie d'une image  
  
1.  [Sélectionnez la partie de l'image](../mfc/selecting-an-area-of-an-image-image-editor-for-icons.md) que vous souhaitez utiliser comme pinceau.  
  
2.  Maintenez la touche **MAJ** enfoncée, cliquez dans la sélection et faites glisser sur l'image.  
  
     \- ou \-  
  
3.  Dans le menu **Image**, sélectionnez **Utiliser la sélection comme pinceau**.  
  
     Votre sélection devient un pinceau personnalisé qui distribue les couleurs dans la sélection sur l'image.  Des copies de la sélection sont déposées le long du chemin de déplacement.  Plus vous faites glisser lentement, plus le nombre de copies est important.  
  
     **Remarque** Si vous cliquez sur **Utiliser la sélection comme pinceau** sans avoir préalablement sélectionné une partie de l'image, l'intégralité de l'image est utilisée comme pinceau.  Le résultat de l'utilisation d'un pinceau personnalisé dépend également du choix d'un [arrière\-plan opaque ou transparent](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).  
  
 Les pixels d'un pinceau personnalisé qui correspondent à la couleur d'arrière\-plan actuelle sont transparents : ils ne sont pas peints sur l'image existante.  Vous pouvez changer ce comportement afin que les pixels de la couleur d'arrière\-plan recouvrent l'image existante.  
  
 Vous pouvez utiliser le pinceau personnalisé comme un tampon ou un stencil pour créer différents effets spéciaux.  
  
#### Pour dessiner des formes de pinceau personnalisé dans la couleur d'arrière\-plan  
  
1.  [Sélectionnez un arrière\-plan opaque ou transparent](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).  
  
2.  [Définissez la couleur d'arrière\-plan](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) en fonction de la couleur avec laquelle vous souhaitez dessiner.  
  
3.  Placez le pinceau personnalisé à l'emplacement où vous souhaitez dessiner.  
  
4.  Cliquez sur le bouton droit de la souris.  Les zones opaques du pinceau personnalisé sont dessinées dans la couleur de l'arrière\-plan.  
  
#### Pour doubler ou diviser en deux la taille d'un pinceau personnalisé  
  
1.  Appuyez sur la touche **SIGNE PLUS** \(**\+**\) pour doubler la taille du pinceau ou sur la touche **SIGNE MOINS** \(**–**\) pour la diviser en deux.  
  
#### Pour annuler un pinceau personnalisé  
  
1.  Appuyez sur **ÉCHAP** ou choisissez un autre outil de dessin.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Configuration requise  
 Aucun  
  
## Voir aussi  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)