---
title: "Adding or Deleting a String | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.string"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strings [C++], adding to string tables"
  - "string tables, deleting strings"
  - "strings [C++], deleting in string tables"
  - "string tables, adding strings"
ms.assetid: 077077b4-0f4b-4633-92d6-60b321164cab
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding or Deleting a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez insérer rapidement de nouvelles entrées dans la table de chaînes à l'aide de l'Éditeur de chaînes.  Les nouvelles chaînes sont placées à la fin de la table et à chacune d'elle est assigné le prochain identificateur disponible.  Vous pouvez ensuite modifier les propriétés ID, Value ou Caption dans la [fenêtre Propriétés](../Topic/Properties%20Window.md).  
  
 L'Éditeur de chaînes s'assure que vous n'utilisez pas un ID en cours d'utilisation.  Si vous sélectionnez un ID en cours d'utilisation, l'Éditeur de chaînes vous avertit et assigne un ID unique générique, par exemple IDS\_STRING58113.  
  
### Pour ajouter une entrée de table de chaînes  
  
1.  Ouvrez la table de chaînes en double\-cliquant sur son icône dans l'[Affichage des ressources](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Si votre projet ne contient pas encore de fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Cliquez avec le bouton droit sur la table de chaînes et choisissez **Nouvelle chaîne** dans le menu contextuel.  
  
3.  Dans l'Éditeur de **chaînes**, sélectionnez un **ID** dans la liste déroulante correspondante ou tapez directement un ID.  
  
4.  Modifiez **Value**, si nécessaire.  
  
5.  Tapez une entrée pour **Caption**.  
  
    > [!NOTE]
    >  Les chaînes null ne sont pas autorisées dans les tables de chaînes Windows.  Si vous créez une entrée dans la table de chaînes qui est une chaîne null, vous recevrez un message vous demandant « Veuillez entrer une chaîne pour cette entrée de table ».  
  
### Pour supprimer une entrée de table de chaînes  
  
1.  Sélectionnez l'entrée que vous souhaitez supprimer.  
  
2.  Dans le menu **Edition**, cliquez sur **Supprimer**.  
  
 \- ou \-  
  
-   Cliquez avec le bouton droit sur la chaîne que vous souhaitez supprimer et choisissez **Supprimer** dans le menu contextuel.  
  
 \- ou \-  
  
-   Appuyez sur la touche **SUPPR**.  
  
 Pour obtenir des informations sur l'ajout de ressources aux projets managés \(ceux qui ciblent le Common Language Runtime\), consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Configuration requise**  
  
 Win32  
  
## Voir aussi  
 [String Editor](../mfc/string-editor.md)   
 [Chaînes](_win32_Strings)   
 [À propos des chaînes](_win32_About_Strings_cpp)