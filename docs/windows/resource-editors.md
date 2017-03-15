---
title: "Resource Editors | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.editors.resource"
  - "vc.resvw.resource.editors"
  - "vs.resvw.resource.editors"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "editors [C++], resource"
  - "editors [C++]"
  - "resource editors"
  - "Windows [C++], application resource editing"
ms.assetid: e20a29ec-d6fb-4ead-98f3-431a0e23aaaf
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Resource Editors
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un éditeur de ressources est un environnement spécialisé pour créer ou modifier des ressources incluses dans un projet Visual Studio. Les éditeurs de ressources de Visual Studio partagent des techniques et des interfaces pour vous aider à créer et à modifier rapidement et facilement des ressources d’application. Les éditeurs de ressources vous permettent d’[afficher et de modifier des ressources dans l’éditeur approprié](../mfc/viewing-and-editing-resources-in-a-resource-editor.md) et d’[afficher un aperçu des ressources](../mfc/previewing-resources.md).  
  
 L’éditeur approprié s’ouvre automatiquement quand vous créez ou que vous ouvrez une ressource.  
  
 **Remarque** comme les projets managés n’utilisent pas de fichiers de script de ressources, vous devez ouvrir vos ressources à partir de **l’Explorateur de solutions**. Vous pouvez utiliser l’[éditeur d’images](../mfc/image-editor-for-icons.md) et l’[éditeur binaire](../mfc/binary-editor.md) pour travailler avec des fichiers de ressources dans des projets managés. Toutes les ressources managées que vous souhaitez modifier doivent être liées. Les éditeurs de ressources Visual Studio ne prennent pas en charge la modification des ressources incorporées.  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
|Utilisez|Pour modifier|  
|--------------|-------------------|  
|[Éditeur d’accélérateurs](../mfc/accelerator-editor.md)|Tables d’accélérateurs dans les projets Visual C\+\+.|  
|[Éditeur binaire](../mfc/binary-editor.md)|Informations de données binaires et ressources personnalisées dans des projets Visual C\+\+, Visual Basic ou Visual C\#.|  
|[Éditeur de boîtes de dialogue](../mfc/dialog-editor.md)|Boîtes de dialogue dans des projets Visual C\+\+.|  
|[Concepteur HTML](../Topic/HTML%20Designer.md)|Pages HTML en mode Création et en mode HTML. Avertissement : vous ne pouvez pas modifier des pages HTML qui se trouvent dans les fichiers EXE ou DLL, car les modifications ne sont pas réimportées dans le fichier EXE ou DLL.|  
|[Éditeur d’images](../mfc/image-editor-for-icons.md)|Bitmaps, icônes, curseurs et autres fichiers image dans des projets Visual C\+\+, Visual Basic ou Visual C\#.|  
|[Éditeur de menus](../mfc/menu-editor.md)|Ressources de menu dans des projets Visual C\+\+.|  
|[Éditeur Ribbon](../mfc/ribbon-designer-mfc.md)|Ressources de ruban dans les projets MFC.|  
|[Éditeur de chaînes](../mfc/string-editor.md)|Tableaux de chaînes dans des projets Visual C\+\+.|  
|[Éditeur de barres d’outils](../mfc/toolbar-editor.md)|Ressources de barre d’outils dans des projets Visual C\+\+. L’éditeur de barres d’outils fait partie de l’éditeur d’images.|  
|[Éditeur d’informations sur la version](../mfc/version-information-editor.md)|Informations de version dans des projets Visual C\+\+.|  
  
## Spécifications  
 Aucun  
  
## Voir aussi  
 [Working with Resource Files](../mfc/working-with-resource-files.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)   
 [Menus et autres ressources](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)