---
title: "Version Information Editor | Microsoft Docs"
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
  - "vc.editors.version.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Version Information editor, about Version Information editor"
  - "editors, Version Information"
  - "resource editors, Version Information editor"
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Version Information Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les informations sur la version sont composées de l’identification de l’entreprise et du produit, d’un numéro de version du produit, et de la notification de copyright et de marque déposée. Avec l’Éditeur d’informations sur la version, vous pouvez créer et tenir à jour ces données, qui sont stockées dans la ressource d’informations sur la version. La ressource d’informations sur la version n’est pas obligatoire pour une application, mais elle est utile pour recueillir des informations qui identifient l’application. Les informations sur la version sont également utilisées par les API d’installation.  
  
 Une ressource d’informations sur la version a un bloc supérieur et un ou plusieurs blocs inférieurs : un bloc d’informations fixes unique en haut et un ou plusieurs blocs d’informations sur la version en bas \(pour les autres langues et\/ou jeux de caractères\). Le bloc supérieur contient des zones numériques modifiables et des listes déroulantes sélectionnables. Les blocs inférieurs contiennent uniquement des zones de texte modifiables.  
  
> [!NOTE]
>  La norme Windows consiste à n’avoir qu’une seule ressource de version, nommée VS\_VERSION\_INFO.  
  
 L’Éditeur d’informations sur la version vous permet de :  
  
-   [Modifier une chaîne dans une ressource d’informations sur la version](../mfc/editing-a-string-in-a-version-information-resource.md)  
  
-   [Ajouter des informations sur la version pour une autre langue \(nouveau bloc d’informations sur la version\)](../mfc/adding-version-information-for-another-language.md)  
  
-   [Supprimer un bloc d’informations sur la version](../mfc/deleting-a-version-information-block.md)  
  
-   [Accéder aux informations sur la version à partir de votre programme](../mfc/accessing-version-information-from-within-your-program.md)  
  
    > [!NOTE]
    >  Quand vous utilisez l’Éditeur d’informations sur la version, dans de nombreux cas vous pouvez cliquer sur le bouton droit de la souris pour afficher un menu contextuel de commandes propres à la ressource. Par exemple, si vous cliquez en pointant sur une entrée d’en\-tête de bloc, le menu contextuel affiche les commandes Nouveau bloc d’informations sur la version et Supprimer un bloc d’informations sur la version.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Spécifications  
 Win32  
  
## Voir aussi  
 [Resource Editors](../mfc/resource-editors.md)   
 [Menus et autres ressources](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)