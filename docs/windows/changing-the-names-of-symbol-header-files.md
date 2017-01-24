---
title: "Changing the Names of Symbol Header Files | Microsoft Docs"
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
  - "vc.editors.symbol.changing.header"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resource files, multiple"
  - "Resource Includes dialog box"
  - "symbol header files, changing names"
  - "symbol header files"
  - "header files, changing names"
  - "names [C++], symbol header files"
  - "symbols, symbol header files"
  - "Resource.h"
ms.assetid: b948284a-7899-402e-ab12-9f2c8480ca9d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing the Names of Symbol Header Files
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Normalement, toutes les définitions de symbole sont enregistrées dans Resource.h.  Toutefois, vous devrez peut\-être changer ce nom de fichier Include pour pouvoir, par exemple, utiliser plusieurs fichiers de ressources dans le même répertoire.  
  
### Pour changer le nom du fichier d'en\-tête de symbole de ressource  
  
1.  Dans [Affichage des ressources](../windows/resource-view-window.md), cliquez avec le bouton droit sur le fichier .rc, puis choisissez [Include des ressources](../windows/resource-includes-dialog-box.md) dans le menu contextuel.  
  
    > [!NOTE]
    >  Si votre projet ne contient pas déjà un fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Dans la zone **Fichier d'en\-tête de symbole**, tapez le nouveau nom du fichier Include.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.*  
  
 Spécifications  
  
 Win32  
  
## Voir aussi  
 [Viewing Resource Symbols](../windows/viewing-resource-symbols.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)