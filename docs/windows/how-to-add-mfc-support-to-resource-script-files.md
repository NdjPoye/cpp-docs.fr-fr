---
title: "How to: Add MFC Support to Resource Script Files | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.resvw.add.MFC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rc files, adding MFC support"
  - ".rc files, adding MFC support"
  - "MFC, adding support to resource scripts files"
  - "resource script files, adding MFC support"
ms.assetid: 599dfe9d-ad26-4e34-899c-49b56599e37f
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# How to: Add MFC Support to Resource Script Files
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Normalement, quand vous générez une application MFC pour Windows à l'aide de l'[Assistant Application MFC](../mfc/reference/mfc-application-wizard.md), l'Assistant génère un ensemble de fichiers de base \(incluant un fichier de script de ressources \(.rc\)\) qui contiennent les principales fonctionnalités MFC \(Microsoft Foundation Classes\).  Toutefois, si vous modifiez un fichier .rc d'une application Windows qui n'est pas basée sur MFC, les fonctionnalités suivantes propres à l'infrastructure MFC ne sont pas disponibles :  
  
-   Assistants Code MFC \(précédemment appelés « [MFC ClassWizard](http://msdn.microsoft.com/fr-fr/98dc2434-ba93-4e0b-b084-1a4bc26cdf1e) »\)  
  
-   Chaînes d'invite de menu  
  
-   Contenu des listes pour les contrôles zone de liste déroulante  
  
-   Hébergement de contrôles ActiveX  
  
 Toutefois, vous pouvez ajouter une prise en charge de MFC aux fichiers .rc existants qui en sont dépourvus.  
  
### Pour ajouter la prise en charge de MFC à des fichiers .rc  
  
1.  Ouvrez le fichier de script de ressources.  
  
    > [!NOTE]
    >  Si votre projet ne contient pas déjà un fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Dans [Affichage des ressources](../windows/resource-view-window.md), sélectionnez le dossier de ressources \(par exemple MFC.rc\).  
  
3.  Dans la fenêtre [Propriétés](../Topic/Properties%20Window.md), affectez à la propriété **MFC Mode** la valeur **True**.  
  
    > [!NOTE]
    >  Outre la définition de cet indicateur, le fichier .rc doit faire partie d'un projet MFC.  Par exemple, il ne suffit pas d'affecter à **MFC Mode** la valeur **True** pour un fichier .rc d'un projet Win32 afin d'accéder aux fonctionnalités MFC.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Spécifications**  
  
 MFC  
  
## Voir aussi  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)