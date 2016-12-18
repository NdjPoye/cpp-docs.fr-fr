---
title: "Symbols: Resource Identifiers | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.identifiers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbols, resource identifiers"
  - "symbols, creating"
  - "resource symbols"
  - "symbols, editing"
  - "resource editors, resource symbols"
ms.assetid: 8fccc09a-0237-4a65-b9c4-57d60c59e324
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Symbols: Resource Identifiers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un symbole est un identificateur de ressource \(ID\) composé de deux parties : une chaîne de texte \(nom du symbole\) mappée à une valeur entière \(valeur du symbole\). Exemple :  
  
```  
IDC_EDITNAME = 5100  
```  
  
 Les noms de symboles sont souvent appelés « identificateurs ».  
  
 Les symboles permettent de faire référence aux ressources et aux objets d’interface utilisateur d’une manière descriptive, à la fois dans votre code source et quand vous travaillez avec eux dans les éditeurs de ressources. Vous pouvez afficher et manipuler les symboles dans un emplacement pratique par le biais de la boîte de dialogue [Symboles des ressources](../windows/viewing-resource-symbols.md).  
  
 Lorsque vous créez une ressource ou un objet de ressource, les [éditeurs de ressources](../mfc/resource-editors.md) fournissent un nom par défaut pour la ressource, par exemple `IDC_RADIO1`, et lui affectent une valeur. La définition nom\-plus\-valeur est stockée dans le fichier Resource.h.  
  
> [!NOTE]
>  Lorsque vous copiez des ressources ou des objets de ressources d’un fichier .rc vers un autre, Visual C\+\+ peut modifier la valeur du symbole de la ressource transférée, ou le nom et la valeur du symbole, pour éviter les conflits avec les noms de symboles ou les valeurs dans le fichier existant.  
  
 Le nombre de ressources et de symboles de votre application augmente à mesure qu’elle augmente en taille et en complexité. Le suivi d’un grand nombre de symboles éparpillés dans plusieurs fichiers peut être difficile. La boîte de dialogue [Symboles des ressources](../windows/resource-symbols-dialog-box.md) simplifie la gestion des symboles en offrant un outil centralisé qui vous permet d’effectuer les tâches suivantes :  
  
-   [Afficher les symboles des ressources](../windows/viewing-resource-symbols.md)  
  
-   [Créer des symboles](../windows/creating-new-symbols.md)  
  
-   [Modifier des symboles non assignés](../windows/changing-unassigned-symbols.md)  
  
-   [Supprimer des symboles non assignés](../windows/deleting-unassigned-symbols.md)  
  
-   [Ouvrir l’Éditeur de ressources pour un symbole donné](../windows/opening-the-resource-editor-for-a-given-symbol.md)  
  
-   [Modifier un symbole ou un nom de symbole \(ID\)](../windows/changing-a-symbol-or-symbol-name-id.md)  
  
-   [Modifier la valeur numérique d’un symbole](../windows/changing-a-symbol-s-numeric-value.md)  
  
-   [Modifier les noms des fichiers d’en\-têtes de symboles](../windows/changing-the-names-of-symbol-header-files.md)  
  
-   [Inclure des symboles partagés \(en lecture seule\) ou calculés](../windows/including-shared-read-only-or-calculated-symbols.md)  
  
-   [Afficher des ID de symboles prédéfinis](../windows/predefined-symbol-ids.md)  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Spécifications  
 Win32  
  
## Voir aussi  
 [How to: Search for Symbols in Resources](../windows/how-to-search-for-symbols-in-resources.md)   
 [Resource Editors](../mfc/resource-editors.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)