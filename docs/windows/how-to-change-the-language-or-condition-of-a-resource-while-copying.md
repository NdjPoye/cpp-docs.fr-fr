---
title: "How to: Change the Language or Condition of a Resource While Copying | Microsoft Docs"
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
  - "vc.resvw.resource.changing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Language property"
  - "condition property of resource"
ms.assetid: 8f622ab0-bac2-468f-ae70-78911afc4759
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Change the Language or Condition of a Resource While Copying
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Durant la copie d'une ressource, vous pouvez changer sa propriété language ou sa propriété condition, ou les deux.  
  
-   La langue de la ressource identifie simplement la langue correspondant à la ressource.  Elle est utilisée par [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042) pour faciliter l'identification de la ressource que vous recherchez.  \(Toutefois, les ressources peuvent présenter des différences spécifiques à chaque langue et qui ne sont pas liées à du texte, par exemple, des accélérateurs qui fonctionnent seulement sur un clavier japonais, ou une image bitmap appropriée uniquement pour les builds localisées en chinois, etc.\)  
  
-   La condition d'une ressource est un symbole défini qui identifie une condition dans laquelle cette copie particulière de la ressource doit être utilisée.  
  
 La langue et la condition d'une ressource sont affichées entre parenthèses après le nom de la ressource dans la fenêtre Espace de travail.  Dans cet exemple, la ressource nommée IDD\_AboutBox utilise le finnois comme langue, et sa condition est XX33.  
  
```  
IDD_AboutBox (Finnish – XX33)  
```  
  
### Pour copier une ressource existante et modifier sa langue ou sa condition  
  
1.  Dans le fichier .rc ou la fenêtre [Affichage des ressources](../windows/resource-view-window.md), cliquez avec le bouton droit sur la ressource à copier.  
  
2.  Dans le menu contextuel, choisissez **Insérer une copie**.  
  
3.  Dans la boîte de dialogue **Insérer une copie de ressources** :  
  
    -   Dans la zone de liste **Langue**, sélectionnez la langue.  
  
    -   Dans la zone **Condition**, tapez la condition.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Spécifications  
  
 Win32  
  
## Voir aussi  
 [How to: Copy Resources](../windows/how-to-copy-resources.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)