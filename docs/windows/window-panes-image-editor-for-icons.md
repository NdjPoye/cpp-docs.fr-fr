---
title: "Window Panes (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.bitmap"
  - "vc.editors.icon"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "graphics editor [C++]"
  - "Image editor [C++], panes"
ms.assetid: d66ea5b3-e2e2-4fc4-aa99-f50022cc690e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Window Panes (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La fenêtre Éditeur d'images affiche deux volets séparés par une barre de fractionnement.  L'un affiche la taille réelle et l'autre une taille agrandie \(facteur d'agrandissement par défaut égal à 6\) de la ressource.  Les affichages dans ces deux volets sont mis à jour automatiquement : les modifications que vous apportez dans un volet sont immédiatement répercutées dans le second volet.  Ces deux volets vous permettent de travailler dans une vue agrandie de votre image, dans laquelle vous pouvez distinguer les pixels, et en même temps, de voir les effets de votre travail sur l'image réelle.  
  
 Le volet gauche utilise autant de place que nécessaire \(jusqu'à la moitié de la fenêtre Image\) pour afficher la vue de votre image avec un facteur d'agrandissement de 1:1 \(par défaut\).  Le volet droit affiche l'image agrandie \(facteur d'agrandissement 6:1 par défaut\).  Vous pouvez [modifier le facteur d'agrandissement](../mfc/changing-the-magnification-factor-image-editor-for-icons.md) dans chaque volet en utilisant l'outil **Loupe** de la [barre d'outils Éditeur d'images](../mfc/toolbar-image-editor-for-icons.md) ou en utilisant les touches accélérateur.  
  
 Vous pouvez agrandir le plus petit volet de la fenêtre Éditeur d'images et utiliser les deux volets pour afficher différentes parties d'une grande image.  Cliquez dans le volet pour le sélectionner.  
  
 Vous pouvez changer les tailles des volets en plaçant le pointeur sur la barre de fractionnement et en déplaçant celle\-ci vers la droite ou vers la gauche.  La barre de fractionnement peut être déplacée afin de n'afficher plus qu'un seul volet.  
  
 Si le volet de l'Éditeur d'images est agrandi 4 fois ou plus, vous pouvez [afficher une grille de pixels](../mfc/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md) qui délimite les pixels individuels dans l'image.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Configuration requise  
 Aucun  
  
## Voir aussi  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)