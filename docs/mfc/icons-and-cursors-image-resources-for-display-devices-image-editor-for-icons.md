---
title: "Icons and Cursors: Image Resources for Display Devices (Image Editor for Icons) | Microsoft Docs"
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
  - "vc.editors.icon"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cursors [C++], creating"
  - "image resources, display devices"
  - "icons [C++], creating"
  - "cursors [C++], types"
  - "icons [C++]"
  - "Image editor [C++], icons and cursors"
  - "cursors [C++]"
  - "display devices, creating icons for"
  - "cursors [C++], hot spots"
  - "icons [C++], types"
ms.assetid: 8f0809a8-0cf0-4da9-b23d-51f28bf15f5b
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Icons and Cursors: Image Resources for Display Devices (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les icônes et curseurs sont des ressources graphiques qui peuvent contenir plusieurs images de différentes tailles et modèles de couleurs pour différents types de périphériques d’affichage. De plus, un curseur a une « zone réactive », l’emplacement utilisé par Windows pour suivre sa position. Vous pouvez créer et modifier des icônes et des curseurs à l’aide de l’Éditeur d’images, comme les bitmaps et autres images.  
  
 Lorsque vous créez une icône ou un curseur, l’Éditeur d’images crée une image d’un type standard. Cette image est remplie initialement avec la couleur d’écran \(transparente\). Si l’image est un curseur, la zone réactive est initialement le coin supérieur gauche \(coordonnées 0,0\).  
  
 Par défaut, l’Éditeur d’images prend en charge la création d’images supplémentaires pour les périphériques répertoriés dans le tableau suivant. Vous pouvez créer des images pour d’autres périphériques en tapant les paramètres de hauteur, largeur et nombre de couleurs dans la boîte de dialogue [Image personnalisée](../mfc/custom-image-dialog-box-image-editor-for-icons.md).  
  
> [!NOTE]
>  Grâce à l'Éditeur d'images, vous pouvez afficher des images 32 bits, mais vous ne pouvez pas les modifier.  
  
|Couleur|Largeur \(pixels\)|Hauteur \(pixels\)|  
|-------------|------------------------|------------------------|  
|Monochrome|16|16|  
|Monochrome|32|32|  
|Monochrome|48|48|  
|Monochrome|64|64|  
|Monochrome|96|96|  
|16|16|16|  
|16|32|32|  
|16|64|64|  
|16|48|48|  
|16|96|96|  
|256|16|16|  
|256|32|32|  
|256|48|48|  
|256|64|64|  
|256|96|96|  
  
-   [Création d’une image de périphérique \(icône ou curseur\)](../mfc/creating-a-device-image-image-editor-for-icons.md)  
  
-   [Ajout d'une image pour un autre périphérique d'affichage](../mfc/adding-an-image-for-a-different-display-device-image-editor-for-icons.md)  
  
-   [Copie d'une image de périphérique](../mfc/copying-a-device-image-image-editor-for-icons.md)  
  
-   [Suppression d'une image de périphérique](../mfc/deleting-a-device-image-image-editor-for-icons.md)  
  
-   [Création de régions transparentes ou inversées dans des images de périphérique](../mfc/creating-transparent-or-inverse-regions-in-device-images.md)  
  
-   [Création d'une icône ou d'un curseur 256 couleurs](../mfc/creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)  
  
-   [Définition de la zone réactive d'un curseur](../mfc/setting-a-cursor-s-hot-spot-image-editor-for-icons.md)  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Spécifications  
 None  
  
## Voir aussi  
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)   
 [Icônes](http://msdn.microsoft.com/library/windows/desktop/ms646973)   
 [Curseurs](http://msdn.microsoft.com/library/windows/desktop/ms646970)