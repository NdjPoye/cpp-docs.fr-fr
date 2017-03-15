---
title: "Symboles des ressources, bo&#238;te de dialogue | Microsoft Docs"
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
  - "vc.editors.resourcesymbols"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Nouveau symbole (boîte de dialogue)"
  - "Symboles des ressources (boîte de dialogue)"
  - "Modifier le symbole (boîte de dialogue)"
ms.assetid: 9706cde3-1f48-4fcd-bedb-2b03b455e3c1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Symboles des ressources, bo&#238;te de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La boîte de dialogue **Symboles des ressources** vous permet d'ajouter de nouveaux symboles des ressources, de changer les symboles affichés, ou d'accéder à l'emplacement où un symbole est utilisé dans le code source.  
  
 **Nom**  
 Affiche le nom du symbole.  Pour plus d'informations, voir [Restrictions relatives au nom de symbole](../windows/symbol-name-restrictions.md).  
  
 **Valeur**  
 Affiche la valeur numérique du symbole.  Pour plus d'informations, voir [Restrictions relatives à la valeur d'un symbole](../windows/symbol-value-restrictions.md).  
  
 **En cours d'utilisation**  
 En cas de sélection, indique que le symbole est utilisé par une ou plusieurs ressources.  La ou les ressources sont répertoriées dans la zone Utilisé par.  
  
 **Afficher les symboles en lecture seule**  
 En cas de sélection, affiche les ressources en lecture seule.  Par défaut, la boîte de dialogue Symboles des ressources affiche uniquement les ressources modifiables dans votre fichier de script de ressources. Toutefois, quand cette option est sélectionnée, les ressources modifiables s'affichent en gras et les ressources en lecture seule s'affichent en texte brut.  
  
 **Utilisé par**  
 Affiche la ou les ressources à l'aide du symbole sélectionné dans la liste des symboles.  Pour passer à l'éditeur pour une ressource donnée, sélectionnez la ressource dans la zone **Utilisé par**, puis cliquez sur **Afficher l'utilisation**.  Pour plus d'informations, voir [Ouverture de l'Éditeur de ressources pour un symbole donné](../windows/opening-the-resource-editor-for-a-given-symbol.md).  
  
 **Nouveau**  
 Ouvre la boîte de dialogue Nouveau symbole, qui vous permet de définir le nom et, si nécessaire, une valeur pour un nouvel identificateur de ressource symbolique.  Pour plus d'informations, voir [Création de symboles](../windows/creating-new-symbols.md).  
  
 **Modifier**  
 Ouvre la boîte de dialogue Modifier le symbole, qui vous permet de changer le nom ou la valeur d'un symbole.  Si le symbole est destiné à un contrôle ou une ressource en cours d'utilisation, il ne peut être modifié qu'à partir de l'éditeur de ressources correspondant.  Pour plus d'informations, voir [Modification des symboles non assignés](../windows/changing-unassigned-symbols.md).  
  
 **Afficher l'utilisation**  
 Ouvre la ressource qui contient le symbole dans l'éditeur de ressources correspondant.  Pour plus d'informations, voir [Ouverture de l'Éditeur de ressources pour un symbole donné](../windows/opening-the-resource-editor-for-a-given-symbol.md).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Spécifications  
 Win32  
  
## Voir aussi  
 [Viewing Resource Symbols](../windows/viewing-resource-symbols.md)