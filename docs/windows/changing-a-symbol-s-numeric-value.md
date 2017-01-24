---
title: "Changing a Symbol&#39;s Numeric Value | Microsoft Docs"
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
  - "vc.editors.symbol.changing.value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numeric values"
  - "symbols, numeric values"
  - "numeric values, changing symbols"
ms.assetid: 468e903b-9c07-4251-ae09-3b6cb754cc2b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing a Symbol&#39;s Numeric Value
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour les symboles associés à une ressource unique, vous pouvez modifier la valeur du symbole à l'aide de la [fenêtre Propriétés](../Topic/Properties%20Window.md).  Vous pouvez utiliser la [boîte de dialogue Symboles des ressources](../windows/resource-symbols-dialog-box.md) pour changer la valeur des symboles qui ne sont pas actuellement assignés à une ressource.  Pour plus d'informations, voir [Modification des symboles non assignés](../windows/changing-unassigned-symbols.md).  
  
### Pour modifier une valeur de symbole assignée à une ressource ou un objet unique  
  
1.  Dans [Affichage des ressources](../windows/resource-view-window.md), sélectionnez la ressource.  
  
    > [!NOTE]
    >  Si votre projet ne contient pas déjà un fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Dans la fenêtre **Propriétés**, tapez le nom du symbole suivi d'un signe égal et d'un entier dans la zone **ID**, par exemple :  
  
    ```  
    IDC_EDITNAME=5100  
    ```  
  
 La nouvelle valeur est stockée dans le fichier d'en\-tête de symbole la prochaine fois que vous enregistrez le projet.  Seul le nom du symbole reste visible dans la zone ID. Le signe égal et la valeur ne sont pas affichés après leur validation.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Spécifications  
  
 Win32  
  
## Voir aussi  
 [Symbol Value Restrictions](../windows/symbol-value-restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)