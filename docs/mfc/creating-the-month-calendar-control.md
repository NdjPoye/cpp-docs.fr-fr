---
title: "Cr&#233;ation du contr&#244;le Month Calendar | Microsoft Docs"
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
  - "CMonthCalCtrl (classe), créer"
  - "calendrier mensuel (contrôles)"
  - "calendrier mensuel (contrôles), créer"
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation du contr&#244;le Month Calendar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comment le contrôle de calendrier month est créé selon que vous utilisez le contrôle dans une boîte de dialogue ou le créez dans une fenêtre sans boîte de dialogue.  
  
### Pour utiliser CMonthCalCtrl directement dans une boîte de dialogue  
  
1.  Dans l'éditeur de boîtes de dialogue, ajoutez un contrôle de calendrier month à la ressource du modèle de la boîte de dialogue.  Spécifiez son ID de contrôle  
  
2.  Spécifiez tous les styles requis, à l'aide de la boîte de dialogue Propriétés du contrôle de calendrier month.  
  
3.  Utilisez l'[Assistant d'Ajout de variable membre](../ide/adding-a-member-variable-visual-cpp.md) pour ajouter une variable membre de type [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md) à la propriété de contrôle.  Vous pouvez utiliser ce membre pour appeler des fonctions membres `CMonthCalCtrl`.  
  
4.  Utilisez la fenêtre Propriétés pour mapper les fonctions de handler dans la classe de la boîte de dialogue pour tous les messages de notification de contrôle de calendrier month que vous devez traiter \(voir [Mapper des messages aux fonctions](../mfc/reference/mapping-messages-to-functions.md)\).  
  
5.  Dans [OnInitDialog](../Topic/CDialog::OnInitDialog.md), définissez les styles supplémentaires pour l'objet `CMonthCalCtrl`.  
  
### Pour utiliser CMonthCalCtrl dans une fenêtre de sans boîte de dialogue.  
  
1.  Définissez le contrôle d'une classe vue ou fenêtre.  
  
2.  Appelez la fonction membre [Créer](../Topic/CMonthCalCtrl::Create.md) du contrôle, éventuellement dans [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), éventuellement dans la fonction gestionnaire [OnCreate](../Topic/CWnd::OnCreate.md) parente de la fenêtre \(si vous sous\-classez le contrôle\).  Définissez les styles pour le contrôle.  
  
## Voir aussi  
 [Utilisation de CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)