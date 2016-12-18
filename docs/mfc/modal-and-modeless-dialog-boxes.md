---
title: "Bo&#238;tes de dialogue modales et non modales | Microsoft Docs"
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
  - "boîtes de dialogue MFC, modales"
  - "boîtes de dialogue MFC, non modales"
  - "boîtes de dialogue modales"
  - "boîtes de dialogue non modales"
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Bo&#238;tes de dialogue modales et non modales
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser la classe [CDialog](../mfc/reference/cdialog-class.md) pour gérer deux types de boîtes de dialogue :  
  
-   *Boîtes de dialogue modales*, qui nécessitent l'utilisateur pour répondre avant de poursuivre le programme  
  
-   *Les boîtes de dialogue non modales*, qui restent à l'écran et sont disponibles à tout moment mais permettent d'autres activités de la part de l'utilisateur  
  
 La modification et les procédures de ressource pour créer un modèle de la boîte de dialogue sont les mêmes pour les boîtes de dialogue modale et non modales.  
  
 Créer d'une boîte de dialogue pour votre application requiert des étapes suivantes :  
  
1.  Utilisez [, l'éditeur de boîtes de dialogue](../mfc/dialog-editor.md) pour concevoir la boîte de dialogue et créer la ressource modèle de la boîte de dialogue.  
  
2.  Créer une boîte de dialogue  
  
3.  Connectez les contrôles de ressources boîte de dialogue [aux gestionnaires de messages](../mfc/adding-event-handlers-for-dialog-box-controls.md) dans la classe de la boîte de dialogue.  
  
4.  Ajouter des membres de données associés aux contrôles de la boîte de dialogue et spécifier les boîtes de dialogue d'échange de données [](../mfc/dialog-data-exchange.md "Dialog Data Exchange") et boîtes de dialogue de validation des données [](../mfc/dialog-data-validation.md "Dialog Data Validation") pour les contrôles.  
  
## Voir aussi  
 [Boîtes de dialogue](../mfc/dialog-boxes.md)   
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)