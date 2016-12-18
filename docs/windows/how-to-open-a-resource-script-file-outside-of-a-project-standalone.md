---
title: "How to: Open a Resource Script File Outside of a Project (Standalone) | Microsoft Docs"
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
  - "vc.editors.resource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], viewing"
  - "rc files, viewing resources"
  - ".rc files, viewing resources"
  - "resource script files, viewing resources"
ms.assetid: bc350c60-178d-4c5d-9a7e-6576b0c936e4
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Open a Resource Script File Outside of a Project (Standalone)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez afficher les ressources contenues dans un fichier .rc sans ouvrir de projet.  Le fichier .rc s'ouvre dans une fenêtre de document au lieu de la fenêtre [Affichage des ressources](../windows/resource-view-window.md) \(ce qui est le cas quand le fichier est ouvert dans un projet\).  
  
> [!NOTE]
>  Cette distinction est importante, car certaines commandes ne sont disponibles qu'au moment où le fichier est ouvert en mode autonome \(en dehors d'un projet\).  Par exemple, vous pouvez uniquement enregistrer un fichier dans un autre format ou sous un autre nom de fichier quand ce fichier est ouvert en dehors d'un projet \(la commande **Enregistrer sous** n'est pas disponible quand un fichier est ouvert dans un projet\).  
  
### Pour ouvrir un fichier .rc en dehors d'un projet  
  
1.  Dans le menu **Fichier**, choisissez **Ouvrir**, puis cliquez sur **Fichier**.  
  
2.  Dans la boîte de dialogue **Ouvrir un fichier**, naviguez jusqu'au fichier de script de ressources à afficher, sélectionnez le fichier, puis cliquez sur **Ouvrir**.  
  
    > [!NOTE]
    >  Si vous ouvrez d'abord le projet \(**Fichier**, **Ouvrir**, **Projet**\), certaines commandes ne seront pas disponibles.  Ouvrir un fichier en mode « autonome » signifie l'ouvrir sans charger d'abord le projet.  
  
 Pour ouvrir et afficher le fichier de ressources au format texte, consultez [Modification d'un fichier de script de ressources \(.rc\)](../windows/how-to-open-a-resource-script-file-in-text-format.md).  
  
#### Pour ouvrir plusieurs fichiers .rc en dehors d'un projet  
  
1.  Ouvrez les deux fichiers de ressources en mode autonome.  Par exemple, ouvrez Source1.rc et Source2.rc.  
  
    1.  Dans le menu **Fichier**, choisissez **Ouvrir**, puis cliquez sur **Fichier**.  
  
    2.  Dans la boîte de dialogue **Ouvrir un fichier**, naviguez jusqu'au premier fichier de script de ressources à ouvrir \(Source1.rc\), sélectionnez le fichier, puis cliquez sur **Ouvrir**.  
  
    3.  Répétez l'étape précédente pour ouvrir le second fichier .rc \(Source2.rc\).  
  
         Les fichiers .rc sont désormais ouverts dans des fenêtres de documents distinctes.  
  
2.  Quand les deux fichiers .rc sont ouverts, disposez\-les fenêtres en mosaïque pour pouvoir les afficher simultanément :  
  
    -   Dans le menu **Fenêtre**, choisissez **Nouveau groupe d'onglets horizontal** ou **Nouveau groupe d'onglets vertical**.  
  
         ou  
  
    -   Cliquez avec le bouton droit sur l'un des fichiers .rc, puis choisissez **Nouveau groupe d'onglets horizontal** ou **Nouveau groupe d'onglets vertical** dans le menu contextuel.  
  
> [!NOTE]
>  Si votre projet ne contient pas déjà un fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Spécifications  
 Win32  
  
## Voir aussi  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)