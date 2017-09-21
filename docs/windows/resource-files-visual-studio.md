---
title: "Resource Files (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio]"
  - ".rc files"
  - "resource files"
  - "resource script files"
  - "resource script files, Win-32 based applications"
  - "resource script files, files updated when editing resources"
  - "resources [Visual Studio], types of resource files"
  - "rct files"
  - "resources [C++]"
  - "rc files"
  - "resource files, types of"
  - ".rct files"
  - "resource script files, unsupported types"
ms.assetid: 4d2b6fcc-07cf-4289-be87-83a60f69533c
caps.latest.revision: 18
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Resource Files (Visual Studio)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Ces informations s’appliquent aux applications de bureau Windows. Pour plus d’informations sur les ressources dans les applications du [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], consultez [Définition des ressources d’application](http://msdn.microsoft.com/fr-fr/476ea844-632c-4467-9ce3-966be1350dd4).  
>   
>  Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Comme les projets écrits dans les langages de programmation .NET managés n’utilisent pas de fichiers de script de ressources, vous devez ouvrir vos ressources à partir de l’**Explorateur de solutions**. Vous pouvez utiliser l’[éditeur d’images](../mfc/image-editor-for-icons.md) et l’[éditeur binaire](../mfc/binary-editor.md) pour travailler avec des fichiers de ressources dans des projets managés. Toutes les ressources managées que vous souhaitez modifier doivent être liées. Les éditeurs de ressources Visual Studio ne prennent pas en charge la modification des ressources incorporées. Pour plus d’informations sur l’ajout manuel de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources aux propriétés, consultez [Procédure pas à pas : localisation de Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Le terme « fichier de ressource » peut faire référence à différents types de fichiers, notamment :  
  
-   Le fichier de script de ressources \(.rc\) d’un programme  
  
-   Un fichier de modèle de ressource \(.rct\)  
  
-   Une ressource individuelle existant en tant que fichier autonome, telle qu’une bitmap, une icône ou un fichier curseur référencé à partir d’un fichier .rc  
  
-   Un fichier d’en\-tête généré par l’environnement de développement, par exemple Resource.h, référencé à partir d’un fichier .rc  
  
 Il existe aussi des ressources dans d’[autres types de fichiers](../windows/editable-file-types-for-resources.md), tels que les fichiers .exe, .dll et .res. Vous pouvez travailler avec des ressources et des fichiers de ressources à partir de votre projet et avec ceux qui ne font pas partie de votre projet actif. Vous pouvez également travailler avec des fichiers de ressources qui n’ont pas été créés dans l’environnement de développement de Visual Studio. Par exemple, vous pouvez :  
  
-   Travailler avec des fichiers de ressources imbriqués et inclus de manière conditionnelle  
  
-   Mettre à jour des ressources existantes ou les convertir au format Visual C\+\+  
  
-   Importer ou exporter des ressources graphiques vers ou à partir de votre fichier de ressources actif  
  
-   Inclure des identificateurs partagés ou en lecture seule  \(symboles\) qui ne peuvent pas être modifiés par l’environnement de développement  
  
-   Inclure dans votre fichier exécutable \(.exe\) des ressources qui ne nécessitent pas de modification \(ou que vous ne voulez pas voir modifiées\) pendant votre projet actif, telles que des ressources partagées entre plusieurs projets  
  
-   Inclure des types de ressources non pris en charge par l’environnement de développement  
  
 Cette section traite des sujets suivants :  
  
-   [Création d’un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md)  
  
-   [Création d’une ressource](../windows/how-to-create-a-resource.md)  
  
-   [Affichage de ressources dans un fichier de script de ressources](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
  
-   [Ouverture d’un fichier de script de ressources au format texte](../windows/how-to-open-a-resource-script-file-in-text-format.md)  
  
-   [Inclusion de ressources au moment de la compilation](../windows/how-to-include-resources-at-compile-time.md)  
  
-   [Copie de ressources](../windows/how-to-copy-resources.md)  
  
-   [Utilisation de modèles de ressources \(.rct\)](../windows/how-to-use-resource-templates.md)  
  
-   [Importation et exportation de ressources](../windows/how-to-import-and-export-resources.md)  
  
-   [Types de fichier modifiables pour les ressources](../windows/editable-file-types-for-resources.md)  
  
-   [Fichiers affectés par la modification des ressources](../windows/files-affected-by-resource-editing.md)  
  
## Spécifications  
 Win32  
  
## Voir aussi  
 [Resource Editors](../mfc/resource-editors.md)   
 [Working with Resource Files](../mfc/working-with-resource-files.md)   
 [Menus et autres ressources](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)