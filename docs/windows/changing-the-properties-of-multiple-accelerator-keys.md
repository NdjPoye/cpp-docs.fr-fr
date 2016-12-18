---
title: "Changing the Properties of Multiple Accelerator Keys | Microsoft Docs"
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
  - "keyboard shortcuts [C++], property changing"
  - "accelerator tables [C++], changing properties"
ms.assetid: b55c9bd6-b430-48bb-b942-0e6f21d7abf9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing the Properties of Multiple Accelerator Keys
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Pour changer les propriétés de plusieurs touches accélérateur  
  
1.  Ouvrez la table d'accélérateurs en double\-cliquant sur son icône dans l'[Affichage des ressources](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Si votre projet ne contient pas encore de fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Sélectionnez les touches accélérateur que vous souhaitez changer en maintenant la touche **CTRL** enfoncée tout en cliquant sur chacune d'elle.  
  
3.  Dans la [fenêtre Propriétés](../Topic/Properties%20Window.md), tapez les valeurs que tous les accélérateurs sélectionnés doivent partager.  
  
    > [!NOTE]
    >  Chaque valeur Modifier s'affiche sous la forme d'une propriété booléenne dans la fenêtre Propriétés.  Si vous changez une valeur [Modifier](../windows/accelerator-modifier-property.md) dans la fenêtre Propriétés, la table d'accélérateurs traite le nouveau modificateur comme un ajout aux modificateurs déjà présents.  C'est pourquoi, si vous définissez des valeurs Modifier, vous devez toutes les définir pour vous assurer que chaque accélérateur partage les paramètres Modifier.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Configuration requise**  
  
 Win32  
  
## Voir aussi  
 [Editing Accelerator Tables](../windows/editing-accelerator-tables.md)   
 [Accelerator Editor](../mfc/accelerator-editor.md)