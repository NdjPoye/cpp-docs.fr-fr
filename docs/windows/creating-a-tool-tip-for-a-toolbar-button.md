---
title: "Creating a Tool Tip for a Toolbar Button | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "tool tips [C++], adding to toolbar buttons"
  - "\n in tool tip"
  - "toolbar buttons [C++], tool tips"
  - "buttons [C++], tool tips"
  - "Toolbar editor, creating tool tips"
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a Tool Tip for a Toolbar Button
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Pour créer une info\-bulle  
  
1.  Sélectionnez le bouton de barre d'outils.  
  
2.  Dans la [fenêtre Propriétés](../Topic/Properties%20Window.md), dans le champ **Prompt**, ajoutez une description du bouton pour la barre d'état ; après le message, ajoutez \\n et le nom de l'info\-bulle.  
  
 Un exemple courant d'info\-bulle est le bouton Imprimer dans WordPad :  
  
 1.  Ouvrez WordPad.  
  
 2.  Placez le pointeur de la souris sur le bouton **Imprimer** de la barre d'outils.  
  
 3.  Remarquez que le mot « Imprimer » s'affiche sous le pointeur de la souris.  
  
 4.  Dans la barre d'état \(en bas de la fenêtre Wordpad\) – le texte « Imprime le document actif » s'affiche.  
  
 La valeur « Imprimer » à l'étape 3 est le « nom de l'info\-bulle » et « Imprime le document actif » à l'étape 4 est la « description du bouton pour la barre d'état ».  
  
 Si vous souhaitez obtenir la même chose en utilisant l'Éditeur de **barres d'outils**, définissez la propriété **Prompt** à **Imprime le document actif\\nImprimer**.  
  
> [!NOTE]
>  Vous pouvez modifier le texte de l'invite en utilisant la [fenêtre Propriétés](../Topic/Properties%20Window.md).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 MFC ou ATL  
  
## Voir aussi  
 [Creating, Moving, and Editing Toolbar Buttons](../mfc/creating-moving-and-editing-toolbar-buttons.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)