---
title: "Setting a Cursor&#39;s Hot Spot (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
helpviewer_keywords: 
  - "cursors, hot spots"
  - "hot spots"
ms.assetid: a610388a-45c8-43cd-98a2-fd31f29238b8
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Setting a Cursor&#39;s Hot Spot (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La zone réactive d'un [curseur](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md) est le point auquel se réfère Windows pour suivre la position du curseur.  Par défaut, la zone réactive correspond au coin supérieur gauche du curseur \(coordonnées 0,0\).  La propriété Hotspot dans la [fenêtre Propriétés](../Topic/Properties%20Window.md) affiche les coordonnées de la zone réactive.  
  
### Pour définir une zone réactive d'un curseur  
  
1.  Dans la [barre d'outils Éditeur d'images](../mfc/toolbar-image-editor-for-icons.md), cliquez sur l'outil **Définir la zone réactive**.  
  
2.  Cliquez sur le pixel que vous souhaitez désigner comme zone réactive pour le curseur.  
  
     La propriété **Hotspot** dans la fenêtre **Propriétés** affiche les nouvelles coordonnées.  
  
    > [!TIP]
    >  Les info\-bulles s'affichent lorsque vous passez votre curseur sur un bouton de barre d'outils.  Ces info\-bulles peuvent vous aider à identifier la fonction de chaque bouton.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 Aucun  
  
## Voir aussi  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)