---
title: "Creating a Device Image (Image Editor for Icons) | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "cursors [C++], creating"
  - "icons [C++], creating"
  - "display devices"
  - "display devices, creating image"
  - "images [C++], creating for display devices"
  - "icons [C++], inserting"
ms.assetid: 5a536928-32df-4ace-beb1-1521ce3b871f
caps.latest.revision: 12
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a Device Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous créez une ressource icône ou curseur, l'Éditeur d'images crée une image d'un style spécifique \(32 x 32, 16 couleurs pour les icônes et 32 x 32, monochrome pour les curseurs\).  Vous pouvez ensuite ajouter des images de différentes tailles et de différents styles à l'icône d'origine et modifier chaque image supplémentaire, selon vos besoins, pour les différents périphériques d'affichage.  Vous pouvez également modifier une image en effectuant une opération de type couper\-coller à partir d'un type d'image existant ou d'une bitmap créée dans un programme graphique.  Pour plus d'informations sur les tailles d'icône que Windows utilise, consultez [Icônes](_win32_Icons_cpp) dans la documentation du Kit de développement logiciel \(SDK\) Windows.  
  
 Lorsque vous ouvrez la ressource icône ou curseur dans l'[Éditeur d'images](../mfc/image-editor-for-icons.md), l'image qui se rapproche le plus du périphérique d'affichage actuel est ouverte par défaut.  
  
### Pour créer une nouvelle icône ou un nouveau curseur  
  
1.  Dans l'[Affichage des ressources](../windows/resource-view-window.md), cliquez avec le bouton droit sur votre fichier .rc, puis sur **Ajouter une ressource** dans le menu contextuel.  \(Si vous disposez déjà d'une ressource image dans votre fichier .rc, par exemple un curseur, vous pouvez cliquer avec le bouton droit sur le dossier **Cursor** et sélectionnez **Insérer Cursor** dans le menu contextuel.\)  
  
    > [!NOTE]
    >  Si votre projet ne contient pas encore de fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Dans la [boîte de dialogue Ajouter une ressource](../windows/add-resource-dialog-box.md), sélectionnez **Icône** ou **Curseur**, puis cliquez sur **Nouveau**.  Pour les icônes, cela crée une ressource icône 16 couleurs, 32 x 32.  Pour les curseurs, une image 32 x 32, monochrome \(2 couleurs\) est créée.  
  
     Si un signe plus \(**\+**\) s'affiche en regard du type de la ressource image dans la boîte de dialogue **Ajouter une ressource**, cela signifie que des modèles de barre d'outils sont disponibles.  Cliquez sur le signe plus pour développer la liste des modèles, sélectionnez un modèle, puis cliquez sur **Nouveau**.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Configuration requise**  
  
 Aucun  
  
## Voir aussi  
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)