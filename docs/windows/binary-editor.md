---
title: "Binary Editor | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.binary.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "editors, Binary"
  - "resources [Visual Studio], editing"
  - "resource editors, Binary editor"
  - "Binary editor"
ms.assetid: 2483c48b-1252-4dbc-826b-82e6c1a0e9cb
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Binary Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!WARNING]
>  L’éditeur binaire n’est pas disponible dans les éditions Express.  
  
 L’éditeur binaire vous permet de modifier n’importe quelle ressource au niveau binaire au format hexadécimal ou ASCII. Vous pouvez également utiliser la [commande Rechercher](../Topic/Find%20Command.md) pour rechercher des chaînes ASCII ou des octets hexadécimaux. Vous devez utiliser l’éditeur binaire uniquement lorsque vous avez besoin d’afficher ou d’apporter des modifications mineures à des ressources personnalisées ou à des types de ressources non pris en charge par l’environnement Visual Studio.  
  
 Pour ouvrir l’éditeur binaire, choisissez **Fichier &#124; Nouveau &#124; Fichier** dans le menu principal, sélectionnez le fichier que vous souhaitez modifier, puis cliquez sur la flèche à côté du bouton **Ouvrir** et choisissez **Ouvrir avec &#124; Éditeur binaire**.  
  
> [!CAUTION]
>  Modifier des ressources telles que des boîtes de dialogue, des images ou des menus dans l’éditeur binaire est une opération dangereuse. Une modification incorrecte peut endommager la ressource et la rendre illisible dans son éditeur natif.  
  
> [!TIP]
>  Quand vous utilisez l’éditeur binaire, dans de nombreux cas vous pouvez cliquer sur le bouton droit de la souris pour afficher un menu contextuel de commandes propres à la ressource. Les commandes disponibles varient selon la cible du pointeur. Par exemple, si vous cliquez en pointant sur l’éditeur binaire avec des valeurs hexadécimales sélectionnées, le menu contextuel affiche les commandes **Couper**, **Copier** et **Coller**.  
  
 Dans l’éditeur binaire, vous pouvez :  
  
-   [Ouvrir une ressource à des fins d’édition binaire](../mfc/opening-a-resource-for-binary-editing.md)  
  
-   [Modifier des données binaires](../mfc/editing-binary-data.md)  
  
-   [Rechercher des données binaires](../mfc/finding-binary-data.md)  
  
-   [Créer une ressource personnalisée ou une ressource de données](../mfc/creating-a-new-custom-or-data-resource.md)  
  
## Ressources managées  
 Vous pouvez utiliser l’[éditeur d’images](../mfc/image-editor-for-icons.md) et l’éditeur binaire pour travailler avec des fichiers de ressources dans des projets managés. Toutes les ressources managées que vous souhaitez modifier doivent être liées. Les éditeurs de ressources Visual Studio ne prennent pas en charge la modification des ressources incorporées.  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Spécifications  
 Aucun  
  
## Voir aussi  
 [Resource Editors](../mfc/resource-editors.md)