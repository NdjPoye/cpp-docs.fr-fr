---
title: "Nouvelle ressource de barre d&#39;outils, bo&#238;te de dialogue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.newtoolbarresource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Nouvelle ressource de barre d'outils (boîte de dialogue)"
ms.assetid: 52dd01ad-e748-4ab2-b3eb-59f5df990ca6
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Nouvelle ressource de barre d&#39;outils, bo&#238;te de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La boîte de dialogue Nouvelle ressource de barre d'outils vous permet de spécifier la largeur et la hauteur des boutons que vous ajoutez à une ressource barre d'outils.  La valeur par défaut est 16 x 15 pixels.  
  
 Une bitmap utilisée pour créer une barre d'outils a une largeur maximale de 2048.  Donc si vous affectez à la **Largeur de bouton** la valeur 512, vous pouvez avoir uniquement quatre boutons.  Si vous définissez la largeur à 513, vous ne disposerez que de trois boutons.  
  
 **Largeur de bouton**  
 Vous permet d'entrer la largeur pour les boutons de barre d'outils lorsque vous convertissez une ressource bitmap en ressource barre d'outils.  Les images sont rognées en fonction de la largeur et de la hauteur spécifiées et les couleurs sont ajustées afin d'utiliser les couleurs de barre d'outils standard \(16 couleurs\).  
  
 **Hauteur de bouton**  
 Vous permet d'entrer la hauteur des boutons de barre d'outils lorsque vous convertissez une ressource bitmap en ressource barre d'outils.  Les images sont rognées en fonction de la largeur et de la hauteur spécifiées et les couleurs sont ajustées afin d'utiliser les couleurs de barre d'outils standard \(16 couleurs\).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Configuration requise  
 MFC ou ATL  
  
## Voir aussi  
 [Toolbar Button Properties](../mfc/toolbar-button-properties.md)   
 [Converting Bitmaps to Toolbars](../mfc/converting-bitmaps-to-toolbars.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)