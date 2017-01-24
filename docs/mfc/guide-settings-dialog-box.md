---
title: "Param&#232;tres du rep&#232;re, bo&#238;te de dialogue | Microsoft Docs"
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
  - "DLU (unités de boîte de dialogue)"
  - "Éditeur de boîtes de dialogue, aligner sur les repères"
  - "espacement de la grille"
  - "repères, paramètres"
  - "unités de boîte de dialogue (DLU)"
  - "grille de présentation dans l'Éditeur de boîtes de dialogue"
  - "aligner sur les repères (Éditeur de boîtes de dialogue)"
  - "contrôles (C++), aligner sur les repères/la grille"
  - "Paramètres du repère (boîte de dialogue de l'Éditeur de boîtes de dialogue)"
ms.assetid: 55381e1c-146a-4fa7-b1b3-b1492817615f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Param&#232;tres du rep&#232;re, bo&#238;te de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Repères de mise en page  
 Affiche les paramètres pour les repères de mise en page.  
  
 **Aucun**  
  
 Masque les outils de mise en page.  
  
 **Règles et repères**  
  
 Lorsque cette option est activée, les règles sont ajoutées aux outils de mise en page et les repères peuvent être placés dans les règles.  Les repères par défaut sont les marges, qui peuvent être déplacées en les faisant glisser.  Cliquez dans les règles pour placer un repère.  Les contrôles « s'alignent » sur les repères lorsque qu'ils sont placés à côtés des repères ou que vous les passez au\-dessus.  Les contrôles sont également déplacés avec un repère une fois qu'ils y sont attachés.  Lorsqu'un contrôle est attaché à un repère sur chaque côté, et qu'un repère est déplacé, le contrôle est redimensionné.  
  
 **Grille**  
  
 Crée une grille.  Les nouveaux contrôles sont automatiquement alignés sur la grille.  
  
## Espacement de la grille  
 Affiche les paramètres pour l'espacement de la grille en unités de boîte de dialogue \(DLU\).  
  
 **Largeur : Unités de boîte de dialogue**  
  
 Définit la largeur de la grille en unités de boîte de dialogue.  Une DLU horizontale correspond à la largeur moyenne de la police de la boîte de dialogue divisée par quatre.  
  
 **Hauteur : Unités de boîte de dialogue**  
  
 Définit la hauteur de la grille en unités de boîte de dialogue.  Une DLU verticale correspond à la hauteur moyenne de la police de la boîte de dialogue divisée par huit.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Configuration requise  
 Win32  
  
## Voir aussi  
 [Modifying the Layout Grid](../mfc/modifying-the-layout-grid.md)   
 [Dialog Editor States \(Guides and Grids\)](../mfc/dialog-editor-states-guides-and-grids.md)