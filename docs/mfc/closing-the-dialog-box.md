---
title: "Fermeture de la bo&#238;te de dialogue | Microsoft Docs"
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
  - "boîtes de dialogue, fermer"
  - "boîtes de dialogue MFC, fermer"
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fermeture de la bo&#238;te de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une boîte de dialogue modale se ferme lorsque l'utilisateur sélectionne un de ses boutons, en général le bouton OK ou le bouton Annuler.  Choisissez Ok ou le bouton Annuler provoque l'envoi par Windows des fenêtres objet une notification de contrôle de **BN\_CLICKED** avec l'ID du bouton, **IDOK** ou **IDCANCEL**.  `CDialog` fournit des fonctions gestionnaires par défaut de ces messages : `OnOK` et `OnCancel`.  Les gestionnaires par défaut appellent la fonction membre de `EndDialog` pour fermer la fenêtre de dialogue.  Vous pouvez également appeler `EndDialog` de votre propre code.  Pour plus d'informations, consultez la fonction membre de [EndDialog](../Topic/CDialog::EndDialog.md) de la classe `CDialog` dans *le guide de MFC*.  
  
 S'arranger pour fermer et supprimer une boîte de dialogue non modales, une substitution `PostNcDestroy` et appeler l'opérateur de **supprimer** sur le pointeur de **this**.  [Destruction de la boîte de dialogue](../mfc/destroying-the-dialog-box.md) décrit ce qui se produit après.  
  
## Voir aussi  
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)