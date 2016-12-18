---
title: "Creating an Icon or Other Image (Image Editor for Icons) | Microsoft Docs"
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
  - "vc.editors.bitmap"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "bitmaps [C++]"
  - "images [C++], creating"
  - "resource toolbars"
  - "resources [Visual Studio], creating images"
  - "bitmaps [C++], creating"
  - "graphics [C++], creating"
  - "Image editor [C++], creating images"
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating an Icon or Other Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez créer une nouvelle image \(bitmap, icône, curseur ou barre d'outils\), puis utiliser l'Éditeur d'images pour personnaliser son apparence.  Vous pouvez également créer une nouvelle bitmap à motifs d'après un [modèle](../windows/how-to-use-resource-templates.md).  
  
### Pour ajouter une nouvelle ressource image à un projet C\+\+ non managé.  
  
1.  Dans l'[Affichage des ressources](../windows/resource-view-window.md), cliquez avec le bouton droit sur votre fichier .rc, puis sur **Ajouter une ressource** dans le menu contextuel.  \(Si vous disposez déjà d'une ressource image dans votre fichier .rc, par exemple un curseur, vous pouvez cliquer avec le bouton droit sur le dossier **Cursor** et sélectionnez **Insérer Cursor** dans le menu contextuel.\)  
  
    > [!NOTE]
    >  **Remarque** Si votre projet ne contient pas déjà de fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Dans la [boîte de dialogue Ajouter une ressource](../windows/add-resource-dialog-box.md), sélectionnez le type de ressource image que vous souhaitez créer \(**Bitmap**, par exemple\), puis cliquez sur **Nouveau**.  
  
     Si un signe plus \(**\+**\) s'affiche en regard du type de la ressource image dans la boîte de dialogue **Ajouter une ressource**, cela signifie que des modèles de barre d'outils sont disponibles.  Cliquez sur le signe plus pour développer la liste des modèles, sélectionnez un modèle, puis cliquez sur **Nouveau**.  
  
### Pour ajouter une nouvelle ressource image à un projet dans un langage de programmation .NET  
  
1.  Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le dossier du projet \(par exemple, **WindowsApplication1**\).  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sélectionnez **Ajouter un nouvel élément**.  
  
3.  Dans le volet **Catégories**, développez le dossier **Éléments de projet local**, puis sélectionnez **Ressources**.  
  
4.  Dans le volet **Modèles**, choisissez le type de ressource que vous souhaitez ajouter à votre projet.  
  
     La ressource est ajoutée à votre projet dans l'Explorateur de solutions. Elle s'ouvre ensuite dans l'[Éditeur d'images](../mfc/image-editor-for-icons.md).  Vous pouvez maintenant utiliser tous les outils disponibles dans l'Éditeur d'images pour modifier votre image.  Pour plus d'informations sur l'ajout d'images à un projet managé, consultez [Chargement d'une image au moment du design \(Windows Forms\)](../Topic/How%20to:%20Load%20a%20Picture%20Using%20the%20Designer%20\(Windows%20Forms\).md).  
  
    > [!NOTE]
    >  Toutes les ressources managées que vous souhaitez modifier doivent être liées.  Les éditeurs de ressources Visual Studio ne prennent pas en charge la modification des ressources incorporées.  Pour plus d'informations, consultez [Création de fichiers de ressources](../Topic/Creating%20Resource%20Files%20for%20Desktop%20Apps.md) dans le document *Guide du développeur .NET Framework*.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 Aucun  
  
## Voir aussi  
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [Converting Bitmaps to Toolbars](../mfc/converting-bitmaps-to-toolbars.md)   
 [Creating New Toolbars](../mfc/creating-new-toolbars.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)