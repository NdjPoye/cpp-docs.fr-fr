---
title: "Changing the Properties of a String | Microsoft Docs"
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
  - "resource identifiers, string properties"
  - "string tables, changing strings"
  - "strings [C++], properties"
ms.assetid: 0a220434-f444-4405-9a64-d28d6b965687
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing the Properties of a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Pour modifier une chaîne ou son identificateur  
  
1.  Ouvrez la table de chaînes en double\-cliquant sur son icône dans l'[Affichage des ressources](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Si votre projet ne contient pas encore de fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Sélectionnez la chaîne que vous souhaitez modifier et double\-cliquez sur la colonne **ID**, **Value** ou **Caption**.  Vous pouvez à présent :  
  
    -   sélectionner un **ID** dans la liste déroulante **ID** ou taper directement un ID ;  
  
    -   taper un chiffre différent dans la colonne **Value** ;  
  
    -   taper des modifications dans la colonne **Caption**.  
  
        > [!NOTE]
        >  Vous pouvez également modifier les propriétés d'une chaîne dans la [fenêtre Propriétés](../Topic/Properties%20Window.md).  
  
 Pour obtenir des informations sur l'ajout de ressources aux projets managés \(ceux qui ciblent le Common Language Runtime\), consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Configuration requise**  
  
 Win32  
  
## Voir aussi  
 [String Editor](../mfc/string-editor.md)   
 [Chaînes](_win32_Strings)   
 [À propos des chaînes](_win32_About_Strings_cpp)