---
title: "Setting the Width of a Horizontal Scroll Bar | Microsoft Docs"
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
  - "list controls, scroll bar width"
  - "CListBox::SetHorizontalExtent"
  - "controls [C++], scroll bar"
  - "scroll bars, displaying in controls"
  - "horizontal scroll bar width"
  - "CListBox class, scroll bar width"
  - "scroll bars, width"
ms.assetid: 51dad141-aa0b-46a3-a82c-46b80d603d94
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Setting the Width of a Horizontal Scroll Bar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous ajoutez une zone de liste avec une barre de défilement horizontale à une boîte de dialogue à l'aide de classes MFC, la barre de défilement ne s'affiche pas automatiquement dans votre application.  
  
### Pour afficher la barre de défilement  
  
1.  Définissez une largeur maximale pour l'élément le plus large en appelant [CListBox::SetHorizontalExtent](../Topic/CListBox::SetHorizontalExtent.md) dans votre code.  
  
     Si cette valeur n'est pas définie, la barre de défilement ne s'affiche pas, même lorsque les éléments de la zone de liste sont plus larges que la zone.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 MFC  
  
## Voir aussi  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Contrôles](../mfc/controls-mfc.md)