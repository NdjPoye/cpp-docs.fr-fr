---
title: "How to: Create a Resource | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "toolbars [C++], resources"
  - "resource toolbars"
  - "resources [Visual Studio], creating"
ms.assetid: aad44914-9145-45a3-a7d8-9de89b366716
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Create a Resource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  L'affichage des ressources n'est pas pris en charge dans les éditions Express.  
  
### Pour créer une ressource dans l’affichage des ressources  
  
1.  Tout en ayant le focus sur votre fichier .rc dans la fenêtre [Affichage des ressources](../windows/resource-view-window.md), cliquez sur le menu **Edition**, puis choisissez **Ajouter une ressource** \(ou cliquez avec le bouton droit sur le fichier .rc dans l'affichage des ressources, puis choisissez **Ajouter une ressource** dans le menu contextuel\).  
  
     [Remarque](../windows/how-to-create-a-resource-script-file.md) Si votre projet ne contient pas déjà un fichier .rc, consultez **Création d'un fichier de script de ressources**.  
  
2.  Dans la [boîte de dialogue Ajouter une ressource](../windows/add-resource-dialog-box.md), choisissez le type de ressource que vous souhaitez ajouter à votre projet.  
  
### Pour créer une ressource dans l’Explorateur de solutions  
  
1.  Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le dossier du projet, choisissez **Ajouter**, puis cliquez sur **Ajouter une ressource** dans le menu contextuel.  
  
     Si vous n'avez pas déjà un fichier .rc dans votre projet, cette étape permet d'en créer un. Vous pouvez ensuite répéter cette étape pour ajouter des types de ressource spécifiques au nouveau fichier .rc.  
  
2.  Dans la [boîte de dialogue Ajouter une ressource](../windows/add-resource-dialog-box.md), choisissez le type de ressource que vous souhaitez ajouter à votre projet.  
  
### Pour créer une ressource dans l’affichage de classes  
  
1.  Dans [Affichage de classes](http://msdn.microsoft.com/fr-fr/8d7430a9-3e33-454c-a9e1-a85e3d2db925), cliquez avec le bouton droit sur la classe, choisissez **Ajouter**, puis cliquez sur **Ajouter une ressource** dans le menu contextuel.  
  
2.  Dans la [boîte de dialogue Ajouter une ressource](../windows/add-resource-dialog-box.md), choisissez le type de ressource que vous souhaitez ajouter à votre projet.  
  
### Pour créer une ressource à partir du menu Projet  
  
1.  Dans le menu **Projet**, choisissez **Ajouter une ressource**.  
  
 Quand vous créez une ressource, Visual C\+\+ lui assigne un nom unique, par exemple IDD\_Dialog1. Vous pouvez personnaliser cet ID de ressource en modifiant les propriétés de la ressource dans l'éditeur de ressources associé ou dans la [fenêtre Propriétés](../Topic/Properties%20Window.md).  
  
 Vous pouvez créer une ressource en tant que ressource par défaut \(une ressource qui n'est pas basée sur un modèle\) ou en tant que ressource inspirée d'un [modèle](../windows/how-to-use-resource-templates.md).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.*  
  
 **Spécifications**  
  
 Win32  
  
## Voir aussi  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)   
 [Ajouter une ressource, boîte de dialogue](../windows/add-resource-dialog-box.md)