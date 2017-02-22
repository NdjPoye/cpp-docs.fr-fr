---
title: "Specifying the Location and Size of a Dialog Box | Microsoft Docs"
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
  - "dialog boxes, size"
  - "dialog boxes, positioning"
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Specifying the Location and Size of a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'emplacement et la taille d'une boîte de dialogue, ainsi que l'emplacement et la taille des contrôles qu'elle contient, sont mesurés en unités de boîte de dialogue.  Les valeurs pour les contrôles individuels et la boîte de dialogue s'affichent dans le coin inférieur droit de la barre d'état Visual Studio lorsque vous les sélectionnez.  
  
 Il existe trois propriétés que vous pouvez définir dans la [fenêtre Propriétés](../Topic/Properties%20Window.md) pour spécifier l'emplacement de la boîte de dialogue à l'écran.  La propriété Center est booléenne ; si vous définissez la valeur à True, la boîte de dialogue s'affiche au centre de l'écran.  Si vous définissez la valeur à False, vous pouvez ensuite définir les propriétés XPos et YPos pour définir explicitement l'emplacement de la boîte de dialogue à l'écran.  Les propriétés de position sont des valeurs offset à partir du coin supérieur gauche de la zone d'affichage, qui est défini à {X\=0, Y\=0}.  Cette position est également basée sur la propriété **Absolute Align** : si elle a la valeur True, les coordonnées sont définies par rapport à l'écran ; si elle a la valeur False, les coordonnées sont définies par rapport à la fenêtre propriétaire de la boîte de dialogue.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Configuration requise  
 Win32  
  
## Voir aussi  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Contrôles](../mfc/controls-mfc.md)