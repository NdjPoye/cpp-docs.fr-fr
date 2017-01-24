---
title: "Composants de bo&#238;te de dialogue dans le Framework | Microsoft Docs"
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
  - "classes de boîte de dialogue, composants de boîte de dialogue"
  - "modèles de boîte de dialogue, infrastructure MFC"
  - "boîtes de dialogue MFC, À propos des boîtes de dialogue MFC"
  - "boîtes de dialogue MFC, créer"
  - "boîtes de dialogue MFC, ressource de boîte de dialogue"
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Composants de bo&#238;te de dialogue dans le Framework
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans l'infrastructure MFC, une boîte de dialogue contient deux composants :  
  
-   Une ressource modèle de la boîte de dialogue qui spécifie les commandes de la boîte de dialogue et leur position.  
  
     La ressource de la boîte de dialogue fournit un modèle de la boîte de dialogue de windows crée la fenêtre de dialogue et l'affiche.  Le modèle spécifie les caractéristiques de la boîte de dialogue, notamment sa taille, emplacement, style, les types et les positions des contrôles de la boîte de dialogue.  Vous utiliserez généralement un modèle de la boîte de dialogue enregistré en tant que ressource, mais vous pouvez également créer votre propre modèle en mémoire.  
  
-   Une classe de la boîte de dialogue, dérivée de [CDialog](../mfc/reference/cdialog-class.md), pour fournir une interface de programmation pour gérer la boîte de dialogue.  
  
     Une boîte de dialogue est une fenêtre et sera jointe dans une fenêtre windows si visible.  Lorsque la fenêtre de dialogue est créée, la ressource modèle de la boîte de dialogue est utilisée comme modèle pour créer des contrôles de fenêtre enfant de la boîte de dialogue.  
  
## Voir aussi  
 [Boîtes de dialogue](../mfc/dialog-boxes.md)   
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)