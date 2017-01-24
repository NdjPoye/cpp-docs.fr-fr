---
title: "How to: Search for Symbols in Resources | Microsoft Docs"
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
  - "symbols, finding"
  - "resources [Visual Studio], searching for symbols"
ms.assetid: 6efef8e8-d0d4-4c49-b895-314974e7791a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Search for Symbols in Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Pour rechercher des symboles dans les ressources  
  
1.  Dans le menu **Edition**, choisissez **Rechercher un symbole**.  
  
2.  Dans la [boîte de dialogue Rechercher un symbole](http://msdn.microsoft.com/fr-fr/63e93d9c-784f-418d-a76a-723da5ff5d96), dans la zone **Rechercher**, sélectionnez une chaîne de recherche antérieure dans la liste déroulante, ou tapez la touche d'accès rapide à rechercher \(par exemple ID\_ACCEL1\).  
  
    > [!TIP]
    >  Pour utiliser des [expressions régulières](../Topic/Using%20Regular%20Expressions%20in%20Visual%20Studio.md) pour votre recherche, vous devez vous servir de la [commande Rechercher dans les fichiers](../Topic/Find%20Command.md) du menu **Edition** au lieu de la commande **Rechercher un symbole**.  Pour permettre l'activation des expressions régulières, la case **Utiliser des expressions régulières** doit être cochée dans la [boîte de dialogue Rechercher](http://msdn.microsoft.com/fr-fr/dad03582-4931-4893-83ba-84b37f5b1600).  Vous pouvez cliquer ensuite sur le bouton représentant une flèche vers la droite, à droite de la zone **Rechercher**, pour afficher une liste des expressions régulières de recherche.  Quand vous sélectionnez une expression dans cette liste, elle se substitue au texte de recherche dans la zone **Rechercher**.  
  
3.  Sélectionnez l'une des options de **recherche**.  
  
4.  Cliquez sur **Suivant**.  
  
    > [!NOTE]
    >  Vous ne pouvez pas rechercher de symboles dans les ressources de type chaîne, accélérateur ou binaire.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Spécifications**  
  
 Win32  
  
## Voir aussi  
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)