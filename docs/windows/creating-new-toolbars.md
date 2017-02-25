---
title: "Creating New Toolbars | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.toolbar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "toolbars [C++], creating"
  - "Toolbar editor, creating new toolbars"
  - "Insert Resource"
ms.assetid: 1b28264b-0718-4df8-9f65-979805d2efef
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Creating New Toolbars
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Pour créer une nouvelle barre d'outils  
  
1.  En mode **Affichage des ressources**, cliquez avec le bouton droit sur le fichier .rc, puis choisissez **Ajouter une ressource** dans le menu contextuel.  \(Si votre fichier .rc contient déjà une barre d'outils, cliquez avec le bouton droit sur le dossier **Toolbar** et sélectionnez **Insérer Toolbar** dans le menu contextuel.\)  
  
     **Remarque** Si votre projet ne contient pas déjà de fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Dans la boîte de dialogue **Ajouter une ressource**, sélectionnez **Barre d'outils** dans la liste **Type de ressource**, puis cliquez sur **Nouveau**.  
  
     Si un signe plus \(\+\) s'affiche en regard du type de ressource **Barre d'outils**, cela signifie que des modèles de barre d'outils sont disponibles.  Cliquez sur le signe plus pour développer la liste des modèles, sélectionnez un modèle, puis cliquez sur **Nouveau**.  
  
     \- ou \-  
  
3.  [Convertit une bitmap existante en barre d'outils](../mfc/converting-bitmaps-to-toolbars.md).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 MFC ou ATL  
  
## Voir aussi  
 [Toolbar Editor](../mfc/toolbar-editor.md)