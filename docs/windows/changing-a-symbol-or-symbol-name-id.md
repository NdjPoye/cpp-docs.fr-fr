---
title: "Changing a Symbol or Symbol Name (ID) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.changing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbol names"
  - "symbols, names"
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Changing a Symbol or Symbol Name (ID)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quand vous créez une ressource ou un objet de ressource, l'environnement de développement lui assigne un nom de symbole par défaut, par exemple, IDD\_DIALOG1.  Vous pouvez utiliser la [fenêtre Propriétés](../Topic/Properties%20Window.md) pour remplacer le nom de symbole par défaut, ou pour changer le nom d'un symbole déjà associé à une ressource.  
  
### Pour changer le nom de symbole d'une ressource  
  
1.  Dans [Affichage des ressources](../windows/resource-view-window.md), sélectionnez la ressource.  
  
    > [!NOTE]
    >  Si votre projet ne contient pas déjà un fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Dans la fenêtre **Propriétés**, tapez un nouveau nom de symbole, ou sélectionnez ce dernier à partir de la liste des symboles existants dans la zone **ID**.  
  
     Si vous tapez un nouveau nom de symbole, il reçoit automatiquement une valeur.  
  
 Vous pouvez utiliser la [boîte de dialogue Symboles des ressources](../windows/resource-symbols-dialog-box.md) pour changer les noms des symboles qui ne sont pas actuellement assignés à une ressource.  Pour plus d'informations, voir [Modification des symboles non assignés](../windows/changing-unassigned-symbols.md).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Spécifications  
  
 Win32  
  
## Voir aussi  
 [Symbol Name Restrictions](../windows/symbol-name-restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)