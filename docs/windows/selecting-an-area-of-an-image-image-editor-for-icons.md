---
title: "Selecting an Area of an Image (Image Editor for Icons) | Microsoft Docs"
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
  - "vc.editors.image.editing"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "Image editor [C++], image selection"
  - "Image editor [C++], selecting images"
  - "images [C++], selecting"
  - "cursors [C++], selecting areas of"
ms.assetid: 8b6ce4ad-eba1-4ece-86ba-cea92c3edff2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Selecting an Area of an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser les outils de sélection pour définir une zone d'une image que vous souhaitez couper, copier, effacer, redimensionner, inverser ou déplacer.  Avec l'outil **Sélection d'un rectangle**, vous pouvez définir et sélectionner une région rectangulaire de l'image.  Avec l'outil **Sélection irrégulière**, vous pouvez dessiner un contour à main levée de la zone que vous souhaitez couper, copier, etc.  
  
> [!NOTE]
>  Consultez les outils **Sélection d'un rectangle** et **Sélection irrégulière** décrits dans la [barre d'outils Éditeur d'images](../mfc/toolbar-image-editor-for-icons.md) ou affichez les info\-bulles associées à chaque bouton dans la barre d'outils **Éditeur d'images**.  
  
 Vous pouvez également créer un pinceau personnalisé à partir d'une sélection.  Pour plus d'informations, consultez [Création d'un pinceau personnalisé](../mfc/creating-a-custom-brush-image-editor-for-icons.md).  
  
### Pour sélectionner une zone d'une image  
  
1.  Dans la barre d'outils **Éditeur d'images** \(ou, dans le menu **Image**, la commande **Outils**\), cliquez sur l'outil de sélection souhaité.  
  
2.  Déplacez le point d'insertion dans un coin de la zone de l'image que vous souhaitez sélectionner.  Un pointeur en forme de croix s'affiche lorsque le point d'insertion se trouve sur l'image.  
  
3.  Faites glisser le point d'insertion vers le coin opposé de la zone que vous souhaitez sélectionner.  Un rectangle montre les pixels qui seront sélectionnés.  Tous les pixels contenus dans le rectangle, y compris ceux qui sont situés sous le rectangle, sont inclus dans la sélection.  
  
4.  Relâchez le bouton de la souris.  La bordure de sélection délimite la zone sélectionnée.  
  
### Pour sélectionner l'intégralité d'une image  
  
1.  Cliquez sur l'image en dehors de la sélection actuelle.  La bordure de sélection change de focus et englobe l'intégralité de l'image.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 Aucun  
  
## Voir aussi  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)