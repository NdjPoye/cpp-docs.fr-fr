---
title: "Cr&#233;ation et affichage de bo&#238;tes de dialogue | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "boîtes de dialogue MFC, créer"
  - "boîtes de dialogue MFC, afficher"
  - "boîtes de dialogue modales, créer"
  - "boîtes de dialogue non modales, créer"
  - "ouvrir des boîtes de dialogue"
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation et affichage de bo&#238;tes de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La création d'un objet de dialogue est une opération biphasée.  D'abord, construisez l'objet de dialogue, puis créez la fenêtre de dialogue.  Les boîtes de dialogue modales et non modales diffèrent dans le processus utilisé pour les créer et les afficher.  Le tableau suivant indique comment les boîtes de dialogue modales et non modales sont normalement construites et affichées.  
  
### Création de dialogue  
  
|Type de dialogue|comment la créer|  
|----------------------|----------------------|  
|[Modeless](../mfc/creating-modeless-dialog-boxes.md)|Construisez `CDialog`, puis appelez la fonction membre **Créer**.|  
|[Modales](../mfc/creating-modal-dialog-boxes.md)|Construisez `CDialog`, puis appelez la fonction membre `DoModal`.|  
  
 Il est possible de créer la boîte de dialogue depuis un [modèle de la boîte de dialogue en mémoire](../mfc/using-a-dialog-template-in-memory.md) que vous avez construit plutôt que depuis une ressource modèle de boîte de dialogue.  Il s'agit d'une rubrique avancée.  
  
## Voir aussi  
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)