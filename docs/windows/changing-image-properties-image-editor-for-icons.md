---
title: "Changing Image Properties (Image Editor for Icons) | Microsoft Docs"
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
  - "images [C++], properties"
  - "Image editor [C++], Properties window"
  - "Image editor [C++], image properties"
  - "Properties window, image editor"
ms.assetid: f6172bf1-08c4-4dfd-b542-dd8749e83fe6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Changing Image Properties (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez définir ou modifier les propriétés d'une image à l'aide de la [fenêtre Propriétés](../Topic/Properties%20Window.md).  
  
### Pour changer les propriétés d'une image  
  
1.  Ouvrez l'image dans l'Éditeur **d'images**.  
  
2.  Dans la fenêtre **Propriétés**, changez les propriétés de l'image.  
  
    |Propriété|Description|  
    |---------------|-----------------|  
    |**Couleurs**|Indique le modèle de couleurs pour l'image.  Sélectionnez Monochrome, 16 ou 256 couleurs ou Couleurs vraies.  Si vous avez déjà dessiné l'image avec une palette 16 couleurs et que vous sélectionnez Monochrome, les couleurs sont remplacées par du noir et blanc.  Le contraste n'est pas toujours conservé : par exemple, des zones adjacentes rouge et verte sont converties en noir.|  
    |**Nom du fichier**|Indique le nom du fichier image.  Par défaut, Visual Studio assigne un nom de fichier de base créé en supprimant les quatre premiers caractères \("IDB\_"\) de l'identificateur de ressource par défaut \(IDB\_BITMAP1\) et en ajoutant l'extension appropriée.  Le nom de fichier pour l'image dans cet exemple est BITMAP1.bmp.  Vous pouvez le renommer MABITMAP1.bmp.|  
    |**Hauteur**|Définit la hauteur de l'image \(en pixels\).  La valeur par défaut est 48.  L'image est rognée ou l'espace est ajouté au\-dessous de l'image existante.|  
    |**ID**|Définit l'identificateur de la ressource.  Par défaut, Microsoft Visual Studio assigne pour une image l'identificateur disponible suivant dans une série : IDB\_BITMAP1, IDB\_BITMAP2, etc.  Des noms identiques sont utilisés pour les icônes et les curseurs.|  
    |**Palette**|Change les propriétés de couleurs.  Double\-cliquez pour sélectionner une couleur et afficher la [boîte de dialogue Affiner les couleurs](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md).  Définissez la couleur en tapant RVB ou NSL dans les zones de texte appropriées.|  
    |**SaveCompressed**|Indique si l'image est dans un format compressé.  Cette propriété est en lecture seule.  Dans Visual Studio, vous ne pouvez pas enregistrer les images dans un format compressé. Lorsque vous créez des images dans Visual Studio, cette propriété a par conséquent la valeur **False**.  Si vous ouvrez une image compressée \(créée dans un autre programme\) dans Visual Studio, cette propriété a la valeur **True**.  Si vous enregistrez une image compressée à l'aide de Visual Studio, elle sera décompressée et cette propriété reprendra la valeur **False**.|  
    |**Largeur**|Définit la largeur de l'image \(en pixels\).  La valeur par défaut pour les bitmaps est 48.  L'image est rognée ou l'espace est ajouté à droite de l'image existante.|  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 Aucun  
  
## Voir aussi  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)