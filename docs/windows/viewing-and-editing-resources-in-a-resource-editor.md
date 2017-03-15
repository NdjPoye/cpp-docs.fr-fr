---
title: "Viewing and Editing Resources in a Resource Editor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.resourceview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], viewing"
  - "rc files, viewing resources"
  - "Resource View pane"
  - "layouts, previewing resource"
  - "code, viewing resources"
  - "resource editors, viewing resources"
  - ".rc files, viewing resources"
  - "resources [Visual Studio], editing"
ms.assetid: ba8bdc07-3f60-43c7-aa5c-d5dd11f0966e
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Viewing and Editing Resources in a Resource Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chaque type de ressource possède un Éditeur de ressources qui lui est propre.  Vous pouvez réorganiser, redimensionner, ajouter des contrôles et des fonctionnalités, ou bien modifier les aspects d'une ressource à l'aide de l'éditeur associé.  Vous pouvez également modifier une ressource au [format texte](../windows/how-to-open-a-resource-script-file-in-text-format.md) et au [format binaire](../mfc/opening-a-resource-for-binary-editing.md).  
  
 Certains types de ressources sont des fichiers individuels qui peuvent être importés et utilisés de plusieurs façons ; ceux\-ci comprennent des fichiers bitmap, icône, curseur, barre d'outils et html.  Ces ressources ont des noms de fichiers et des [identificateurs de ressources](../mfc/symbols-resource-identifiers.md).  D'autres, telles que les boîtes de dialogue, les menus et les tables de chaîne des projets Win32, existent uniquement en tant que partie d'un fichier de script de ressources \(.rc\) ou d'un fichier modèle de ressources \(.rct\).  
  
> [!NOTE]
>  Les propriétés d'une ressource [peuvent être modifiées rapidement à l'aide de la fenêtre Propriétés](../windows/changing-the-properties-of-a-resource.md).  
  
## Ressources Win32  
 Vous pouvez accéder aux ressources Win32 dans le volet [Affichage des ressources](../windows/resource-view-window.md).  
  
#### Pour afficher une ressource Win32 dans un Éditeur de ressources  
  
1.  Dans le menu **Affichage**, cliquez sur **Affichage des ressources**.  
  
2.  Si la fenêtre Affichage des ressources n'est pas la fenêtre de premier niveau, cliquez sur l'onglet **Affichage des ressources** pour l'amener au premier plan.  
  
3.  Dans l'Affichage des ressources, développez le dossier pour le projet qui contient les ressources à afficher.  Par exemple, si vous souhaitez afficher une ressource de boîte de dialogue, développez le dossier Boîte de dialogue.  
  
    > [!NOTE]
    >  Si votre projet ne contient pas encore de fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
4.  Double\-cliquez sur la ressource, par exemple, IDD\_ABOUTBOX.  
  
     La ressource s'ouvre dans l'éditeur approprié.  Par exemple, pour les ressources de boîte de dialogue, la ressource s'ouvre dans l'Éditeur de boîtes de dialogue.  
  
     Vous pouvez également [afficher les ressources d'un fichier .rc \(script de ressources\) sans ouvrir de projet](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
#### Pour supprimer une ressource Win 32 existante  
  
1.  Dans l'Affichage des ressources, développez le nœud pour un type de ressource.  
  
2.  Cliquez avec le bouton droit sur la ressource que vous souhaitez supprimer, puis sélectionnez **Supprimer** dans le menu contextuel.  
  
    > [!NOTE]
    >  Vous pouvez supprimer une ressource en vous servant de la même commande du menu contextuel lorsque le fichier .rc est ouvert dans une fenêtre de document en dehors d'un projet.  
  
## Ressources des projets managés  
 Dans la mesure où les projets managés n'utilisent pas de fichiers de script de ressources, vous devez ouvrir vos ressources à partir de l'**Explorateur de solutions**.  Vous pouvez utiliser l'[Éditeur d'images](../mfc/image-editor-for-icons.md) et l'[Éditeur binaire](../mfc/binary-editor.md) conjointement aux fichiers de ressources dans les projets managés.  Toutes les ressources managées que vous souhaitez modifier doivent être liées.  Les éditeurs de ressources Visual Studio ne prennent pas en charge la modification des ressources incorporées.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
#### Pour afficher une ressource managée dans un Éditeur de ressources  
  
1.  Dans l'Explorateur de solutions, double\-cliquez sur la ressource, par exemple Bitmap1.bmp.  
  
     La ressource s'ouvre dans l'éditeur approprié.  
  
#### Pour supprimer une ressource managée existante  
  
1.  Dans l'Explorateur de solutions, cliquez avec le bouton droit sur la ressource que vous souhaitez supprimer et choisissez **Supprimer** dans le menu contextuel.  
  
### Configuration requise  
 Aucun  
  
## Voir aussi  
 [Resource Editors](../mfc/resource-editors.md)