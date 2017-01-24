---
title: "Finding a String | Microsoft Docs"
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
  - "strings [C++], searching"
  - "strings [C++]"
ms.assetid: c2497173-f356-4f77-97d6-f0ac41782510
caps.latest.revision: 12
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Finding a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez rechercher une ou plusieurs chaînes dans la table de chaînes et utiliser des [expressions régulières](../Topic/Using%20Regular%20Expressions%20in%20Visual%20Studio.md) à l'aide de la commande **Rechercher dans les fichiers** \(menu **Edition**\) pour rechercher toutes les instances des chaînes qui correspondent à un critère de recherche.  
  
### Pour rechercher une chaîne dans la table de chaînes  
  
1.  Ouvrez la table de chaînes en double\-cliquant sur son icône dans l'[Affichage des ressources](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Si votre projet ne contient pas encore de fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Dans le menu **Edition**, cliquez sur **Rechercher et remplacer**, puis sur **Rechercher**.  
  
3.  Dans la zone **Rechercher**, sélectionnez une chaîne recherchée dans la liste déroulante ou tapez le texte de la légende ou l'identificateur de ressource de la chaîne à rechercher.  
  
4.  Sélectionnez l'une des options **Rechercher**.  
  
5.  Cliquez sur **Suivant**.  
  
    > [!TIP]
    >  Pour utiliser des expressions régulières lorsque vous recherchez des fichiers, utilisez la commande **Rechercher dans les fichiers**.  Tapez une expression régulière correspondant à un critère ou cliquez sur le bouton à droite de la zone **Rechercher** pour afficher une liste des expressions régulières de recherche.  Lorsque vous avez sélectionné une expression dans la liste, elle se substitue au texte de recherche dans la zone **Rechercher**.  Si vous utilisez des expressions régulières, assurez\-vous que la case à cocher **Utiliser : Expressions régulières** est activée.  
  
 Pour obtenir des informations sur l'ajout de ressources aux projets managés \(ceux qui ciblent le Common Language Runtime\), consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Configuration requise**  
  
 Win32  
  
## Voir aussi  
 [String Editor](../mfc/string-editor.md)   
 [Chaînes](_win32_Strings)   
 [À propos des chaînes](_win32_About_Strings_cpp)