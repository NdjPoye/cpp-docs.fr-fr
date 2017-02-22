---
title: "Editing a String in a Version Information Resource | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "version information resources"
  - "resources [Visual Studio], editing version information"
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Editing a String in a Version Information Resource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Pour modifier une chaîne dans une ressource d’informations sur la version  
  
1.  Cliquez sur l’élément pour le sélectionner, puis recliquez dessus pour commencer à le modifier. Apportez les modifications directement dans la table d’informations sur la version ou dans la fenêtre [Propriétés](../Topic/Properties%20Window.md). Les modifications que vous apportez apparaîtront aux deux emplacements.  
  
     **Remarque** Lors de la modification de la clé **FILEFLAGS** dans l’Éditeur d’informations sur la version, vous remarquerez que vous ne pouvez pas définir les propriétés **Debug**, **Private Build** ou **Special Build** \(dans la fenêtre Propriétés\) pour les fichiers .rc :  
  
    -   L’Éditeur d’informations sur la version définit la propriété **Debug** avec un \#ifdef dans le script de ressources, en fonction de l’indicateur de build **\_DEBUG**.  
  
    -   Si la clé **Private Build** a une **Valeur** définie dans la table d’informations sur la version, la propriété **Private Build** correspondante \(dans la fenêtre Propriétés\) de la clé **FILEFLAGS** a la valeur **True**. Si la **Valeur** est vide, la propriété est **False**. De même, la clé **Special Build** \(dans la table d’informations sur la version\) est liée à la propriété **Special Build** de la clé **FILEFLAGS**.  
  
 Vous pouvez trier la séquence d’informations du bloc de chaîne en cliquant sur l’en\-tête de colonne Clé ou Valeur. Ces en\-têtes réorganisent automatiquement les informations dans la séquence sélectionnée.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Spécifications**  
  
 Win32  
  
## Voir aussi  
 [Version Information Editor](../mfc/version-information-editor.md)   
 [Informations sur la version \(Windows\)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)