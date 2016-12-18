---
title: "Aligning Controls on a Guide | Microsoft Docs"
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
  - "DLUs (dialog units)"
  - "controls [C++], aligning"
  - "Dialog editor, snap to guides"
  - "guides, tick mark interval"
  - "dialog box controls, placement"
  - "guides, aligning controls"
  - "dialog units (DLUs)"
  - "snap to guides (Dialog editor)"
  - "controls [C++], sizing"
  - "tick mark interval in Dialog editor"
  - "controls [C++], snap to guides/grid"
ms.assetid: 17db84ba-5288-4478-be57-afa748aa6447
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Aligning Controls on a Guide
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les poignées de dimensionnement des contrôles s'alignent sur les repères lorsque les contrôles sont déplacés et les repères s'alignent sur les contrôles \(si aucun contrôle n'a été précédemment aligné sur le repère\).  Lorsqu'un repère est déplacé, les contrôles dont ils dépendent, sont également déplacés.  Les contrôles alignés sur plusieurs repères sont redimensionnés lorsqu'un repère est déplacé.  
  
 Les graduations dans les règles qui déterminent l'espacement des repères et des contrôles sont définies par les unités de boîte de dialogue \(DLU\).  Une DLU est basée sur la taille de la police de la boîte de dialogue, en règle générale MS Shell Dlg 8 points.  Une DLU horizontale correspond à la largeur moyenne de la police de la boîte de dialogue divisée par quatre.  Une DLU verticale correspond à la hauteur moyenne de la police divisée par huit.  
  
### Pour dimensionner un groupe de contrôles avec des repères  
  
1.  Alignez un côté du contrôle \(ou des contrôles\) sur un repère.  
  
2.  Faites glisser un repère vers l'autre côté du contrôle \(ou des contrôles\).  
  
     Si nécessaire, avec plusieurs contrôles, vous pouvez les aligner un par un sur le deuxième repère.  
  
3.  Déplacez l'un des repères pour dimensionner le contrôle \(ou les contrôles\).  
  
### Pour changer les intervalles entre les graduations  
  
1.  Dans le menu **Format**, cliquez sur **Paramètres du repère**.  
  
2.  Dans la [boîte de dialogue Paramètres du repère](../mfc/guide-settings-dialog-box.md), dans le champ **Espacement de la grille**, spécifiez une nouvelle largeur et une nouvelle hauteur en unités de boîte de dialogue.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 Win32  
  
## Voir aussi  
 [Dialog Editor States \(Guides and Grids\)](../mfc/dialog-editor-states-guides-and-grids.md)   
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)