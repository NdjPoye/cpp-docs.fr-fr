---
title: "Moving a String from One Resource File to Another | Microsoft Docs"
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
  - "strings [C++], moving between files"
  - "resource script files, moving strings"
  - "string editing, moving strings between resources"
  - "String editor, moving strings between files"
ms.assetid: 94f8ee81-9b4c-4788-ba95-68c58db38029
caps.latest.revision: 12
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Moving a String from One Resource File to Another
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Pour déplacer une chaîne d'un fichier de script de ressources vers un autre  
  
1.  Ouvrez les tables de chaînes dans les deux fichiers .rc.  Pour plus d'informations, consultez [Ouverture d'un fichier de script de ressources en dehors d'un projet \(autonome\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
    > [!NOTE]
    >  Si votre projet ne contient pas encore de fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Cliquez avec le bouton droit sur la chaîne que vous souhaitez déplacer et choisissez **Couper** dans le menu contextuel.  
  
3.  Placez le curseur dans la fenêtre cible **Éditeur de chaînes**.  
  
4.  Dans le fichier .rc vers lequel vous souhaitez déplacer la chaîne, cliquez avec le bouton droit et choisissez **Coller** dans le menu contextuel.  
  
    > [!NOTE]
    >  Si l'ID \(**ID**\) ou la valeur \(**value**\) de la chaîne déplacée est en conflit avec des **ID** ou **valeurs** existants du fichier de destination, l'**ID** ou la **valeur** de la chaîne déplacée sont modifiés.  S'il existe une chaîne ayant le même **ID**, l'**ID** de la chaîne déplacée change.  S'il existe une chaîne ayant la même **valeur**, la **valeur** de la chaîne déplacée change.  
  
 Pour obtenir des informations sur l'ajout de ressources aux projets managés \(ceux qui ciblent le Common Language Runtime\), consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Configuration requise**  
  
 Win32  
  
## Voir aussi  
 [String Editor](../mfc/string-editor.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Personnalisation des dispositions de fenêtres](../Topic/Customizing%20window%20layouts%20in%20Visual%20Studio.md)   
 [Chaînes](_win32_Strings)   
 [À propos des chaînes](_win32_About_Strings_cpp)