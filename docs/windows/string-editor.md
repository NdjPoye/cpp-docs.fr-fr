---
title: "String Editor | Microsoft Docs"
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
  - "vc.editors.string.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "String editor"
  - "string tables"
  - "string tables, String editor"
  - "string editing"
  - "string editing, string tables"
  - "resource editors, String editor"
  - "strings [C++], editing"
ms.assetid: f71ab8de-3068-4e29-8e28-5a33d18dd416
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# String Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une table de chaînes est une ressource Windows qui contient une liste d’ID, de valeurs et de légendes pour toutes les chaînes de votre application. Par exemple, les invites de la barre d’état figurent dans la table de chaînes.  
  
 Lors du développement d’une application, vous pouvez avoir plusieurs tables de chaînes, une pour chaque langue ou condition. Toutefois, un module exécutable n’a qu’une seule table de chaînes. Une application en cours d’exécution peut faire référence à plusieurs tables de chaînes si vous placez les tables dans différentes DLL.  
  
 Les tables de chaînes simplifient la localisation de votre application dans différentes langues. Si toutes les chaînes sont dans une table de chaînes, vous pouvez localiser l’application en traduisant les chaînes \(et autres ressources\) sans modifier le code source. Il est généralement préférable de procéder ainsi plutôt que de rechercher et de remplacer manuellement différentes chaînes dans les fichiers sources.  
  
 Avec l’Éditeur de chaînes, vous pouvez :  
  
-   [Rechercher une ou plusieurs chaînes](../mfc/finding-a-string.md)  
  
-   [Insérer rapidement de nouvelles entrées](../mfc/adding-or-deleting-a-string.md) dans la table de chaînes  
  
-   [Déplacer une chaîne d’un fichier de ressources vers un autre](../mfc/moving-a-string-from-one-resource-file-to-another.md)  
  
-   [Utiliser la modification sur place pour les propriétés ID, Value et Caption](../mfc/changing-the-properties-of-a-string.md) et afficher immédiatement les modifications  
  
-   [Modifier la propriété de légende de plusieurs chaînes](../mfc/changing-the-caption-property-of-multiple-strings.md)  
  
-   [Ajouter des caractères de mise en forme ou des caractères spéciaux à une chaîne](../mfc/adding-formatting-or-special-characters-to-a-string.md)  
  
    > [!NOTE]
    >  Windows n’autorise pas la création de tables de chaînes vides. Si vous créez une table de chaînes sans entrée, elle est supprimée automatiquement lorsque vous enregistrez le fichier de ressources.  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés \(ceux qui ciblent le Commun Langage Runtime\), consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Spécifications  
 Win32  
  
## Voir aussi  
 [Resource Editors](../mfc/resource-editors.md)   
 [Chaînes](http://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)   
 [À propos des chaînes](http://msdn.microsoft.com/library/windows/desktop/ms647465.aspx)