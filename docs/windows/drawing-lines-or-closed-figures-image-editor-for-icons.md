---
title: "Drawing Lines or Closed Figures (Image Editor for Icons) | Microsoft Docs"
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
  - "closed figures, drawing"
  - "lines [C++], painting"
  - "lines [C++], drawing"
  - "Image editor [C++], drawing lines"
  - "shapes, drawing"
ms.assetid: 7edd86db-77b1-451f-8001-bbfed9c6304f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Drawing Lines or Closed Figures (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les outils de l'Éditeur d'images pour dessiner des lignes ou des figures fermées fonctionnent tous de la même façon : vous placez le point d'insertion à un endroit et faites glisser vers un autre.  Pour les lignes, ces points sont les extrémités.  Pour les figures fermées, ces points sont les coins opposés d'un rectangle qui délimite la figure.  
  
 Les lignes sont dessinées selon une largeur déterminée par la sélection de pinceau actuelle et les figures encadrées sont dessinées selon une largeur déterminée par la sélection de largeur actuelle.  Les lignes et toutes les figures, encadrées et remplies, sont dessinées dans la couleur de premier plan si vous appuyez sur le bouton gauche, ou dans la couleur d'arrière\-plan si vous utilisez le bouton droit.  
  
### Pour dessiner une ligne  
  
1.  Dans la [barre d'outils Éditeur d'images](../mfc/toolbar-image-editor-for-icons.md) \(ou dans le menu **Image**, la commande **Outils**\), cliquez sur l'outil **Ligne**.  
  
2.  Si nécessaire, sélectionnez les couleurs et un pinceau :  
  
    -   Dans la [palette Couleurs](../windows/colors-window-image-editor-for-icons.md), cliquez avec le bouton gauche pour sélectionner une couleur de premier plan ou avec le bouton droit pour sélectionner une couleur d'arrière\-plan.  
  
    -   Dans le [sélecteur d'options](../mfc/toolbar-image-editor-for-icons.md), cliquez sur une forme représentant le pinceau à utiliser.  
  
3.  Placez le pointeur au point de départ de la ligne.  
  
4.  Faites glisser jusqu'à l'extrémité de la ligne.  
  
### Pour dessiner une figure fermée  
  
1.  Dans la barre d'outils **Éditeur d'images** \(ou, dans le menu **Image**, la commande **Outils**\), cliquez sur un outil **Dessin de figure fermée**.  
  
     Les outils **Dessin de figure fermée** créent des figures comme indiqué par leur bouton respectif.  
  
2.  Si nécessaire, sélectionnez des couleurs et une largeur de ligne.  
  
3.  Déplacez le pointeur vers un coin de la zone rectangulaire dans laquelle vous souhaitez dessiner la figure.  
  
4.  Faites glisser le pointeur en diagonale vers le coin opposé.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 Aucun  
  
## Voir aussi  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)   
 [Working with Color](../mfc/working-with-color-image-editor-for-icons.md)