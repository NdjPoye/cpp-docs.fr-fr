---
title: "Saving Bitmaps as GIFs or JPEGs (Image Editor for Icons) | Microsoft Docs"
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
  - "vc.editors.image.editing"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - ".gif files, saving bitmaps as"
  - "jpg files, saving bitmaps as"
  - "jpeg files, saving bitmaps as"
  - ".jpg files, saving bitmaps as"
  - "Image editor [C++], converting image formats"
  - "gif files, saving bitmaps as"
  - "bitmaps [C++], converting formats"
  - ".jpeg files, saving bitmaps as"
  - "graphics [C++], converting formats"
  - "images [C++], converting formats"
ms.assetid: 115df69f-10fb-4e6f-906b-853c1e4a54af
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Saving Bitmaps as GIFs or JPEGs (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous créez une bitmap, l'image est créée au format bitmap \(.bmp\).  Cependant, vous pouvez enregistrer l'image au format GIF ou JPEG ou dans un autre format graphique.  
  
> [!NOTE]
>  Ce processus ne s'applique pas aux icônes et aux curseurs.  
  
### Pour créer et enregistrer une bitmap au format .gif ou .jpeg  
  
1.  Dans le menu **Fichier**, sélectionnez **Ouvrir**, puis cliquez sur **Fichier**.  
  
2.  Dans la **boîte de dialogue Nouveau fichier**, cliquez sur le dossier **Visual C\+\+**, sélectionnez **Fichier bitmap \(.bmp\)** dans la zone **Modèles**, puis cliquez sur **Ouvrir**.  
  
     La bitmap s'ouvre dans l'Éditeur **d'images**.  
  
3.  Apportez les modifications souhaitées à la bitmap.  
  
4.  Lorsque la bitmap est ouverte dans l'Éditeur **d'images**, cliquez sur **Enregistrer *nomfichier*.bmp sous** dans le menu **Fichier**.  
  
5.  Dans la boîte de dialogue **Enregistrer le fichier sous**, tapez dans la zone **Nom de fichier** le nom souhaité et l'extension correspondant au format de fichier que vous souhaitez utiliser.  Par exemple, monfichier.gif.  
  
     **Remarque**  Vous devez créer ou ouvrir la bitmap en dehors de votre projet afin de l'enregistrer dans un autre format de fichier.  Si vous la créez ou l'ouvrez dans votre projet, la commande **Enregistrer sous** n'est pas disponible.  Pour plus d'informations, consultez [Ouverture d'un fichier de script de ressources en dehors d'un projet \(autonome\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
6.  Cliquez sur **Enregistrer**.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Voir aussi  
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)