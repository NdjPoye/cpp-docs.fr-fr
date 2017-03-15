---
title: "Utilisation d&#39;un contr&#244;le Tab | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabCtrl (classe), utilisation"
  - "contrôles onglet, utilisation"
  - "contrôles onglet, utiliser"
ms.assetid: 819488e3-4944-44b7-9483-195edb8e0aed
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Utilisation d&#39;un contr&#244;le Tab
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La façon la plus simple d'utiliser un contrôle onglet \([CTabCtrl](../mfc/reference/ctabctrl-class.md)\) est de l'ajouter à une ressource modèle de boîte de dialogue avec l'éditeur de boîtes de dialogue.  Vous pouvez également utiliser un contrôle onglet seul.  MFC appelle **InitCommonControls** pour vous.  Les tâches principales sont les suivantes :  
  
-   [Création du contrôle Tab](../mfc/creating-the-tab-control.md)  
  
-   [Ajout d'onglets à un contrôle Tab](../mfc/adding-tabs-to-a-tab-control.md)  
  
-   [Traitement des messages de notification du contrôle Tab](../mfc/processing-tab-control-notification-messages.md)  
  
 Si l'objet de contrôle onglet est incorporé dans une vue ou une classe de boîte de dialogue parente, le contrôle est détruit lorsque le parent est détruit.  
  
## Voir aussi  
 [Utilisation de CTabCtrl](../mfc/using-ctabctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)